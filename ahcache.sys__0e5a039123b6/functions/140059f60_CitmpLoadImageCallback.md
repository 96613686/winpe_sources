# CitmpLoadImageCallback

- ea: `0x140059f60`
- end: `0x14005a22d`
- name: `CitmpLoadImageCallback`
- size: `717`
- prototype: `void __fastcall(PUNICODE_STRING FullImageName, HANDLE ProcessId, PIMAGE_INFO ImageInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003a58`
- `0x14003e364`
- `0x140059f60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005a01d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a01d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a036`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a036`
- `ntoskrnl!ExAllocatePool2` at `0x14005a1ac`
- `ntoskrnl!ExAllocatePool2` at `0x14005a1ac`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140059fa4`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140059fa4`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140059f87`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140059f87`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005a106`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005a106`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14005a136`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14005a136`
- `ntoskrnl!SeLocateProcessImageName` at `0x14005a17d`
- `ntoskrnl!SeLocateProcessImageName` at `0x14005a17d`
- `ntoskrnl!ObfReferenceObject` at `0x14005a1da`
- `ntoskrnl!ObfReferenceObject` at `0x14005a1da`
- `ntoskrnl!ExQueueWorkItem` at `0x14005a214`
- `ntoskrnl!ExQueueWorkItem` at `0x14005a214`

## string_xrefs

- `0x14005a18d`: `Failed to read process name [%x]`

## pseudocode

```c
void __fastcall CitmpLoadImageCallback(PUNICODE_STRING FullImageName, HANDLE ProcessId, PIMAGE_INFO ImageInfo)
{
  void *CurrentServerSilo; // r14
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // ebx
  int v13; // ebp
  struct _LIST_ENTRY *v14; // rdi
  __int64 Flink_low; // rdx
  unsigned int Length; // eax
  __int64 v17; // rcx
  wchar_t *Buffer; // rax
  NTSTATUS ProcessImageName; // eax
  const char *v20; // r9
  __int64 v21; // r8
  struct _WORK_QUEUE_ITEM *Pool2; // rbx
  __int64 v23; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-40h] BYREF
  PVOID P; // [rsp+80h] [rbp+8h] BYREF
  PVOID Object; // [rsp+98h] [rbp+20h] BYREF

  Object = 0;
  P = 0;
  v23 = 0;
  CurrentServerSilo = (void *)PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)g_AhcacheSiloContextSlot, &v23);
  P = 0;
  Object = 0;
  if ( FullImageName && ProcessId && ImageInfo )
  {
    if ( ImageInfo == (PIMAGE_INFO)8 )
    {
      AslLogCallPrintf(1, "CitmpLoadImageCallback", 231, "Invalid ImageInfo, no IMAGE_INFO_EX found");
      goto LABEL_6;
    }
    v7 = *(_QWORD *)&ImageInfo[1].Properties;
    if ( !v7 )
    {
      AslLogCallPrintf(1, "CitmpLoadImageCallback", 241, "Invalid FileObject");
      goto LABEL_6;
    }
    v8 = *(_QWORD *)(v7 + 16);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v8 + 16);
      if ( v9 )
      {
        if ( (*(_DWORD *)(v9 + 48) & 0x200000) != 0 )
        {
          v10 = CitmpComputeFileNameHash(&FullImageName->Length);
          v11 = v23;
          v12 = 0;
          v13 = v10;
          if ( !*(_DWORD *)(v23 + 656) )
            goto LABEL_6;
          while ( 1 )
          {
            v14 = (struct _LIST_ENTRY *)(*(_QWORD *)(v11 + 648) + 24LL * v12);
            if ( LODWORD(v14[1].Flink) == v13 )
            {
              Flink_low = LOWORD(v14->Flink);
              Length = FullImageName->Length;
              String1 = 0;
              if ( (unsigned __int16)Length >= (unsigned __int16)Flink_low )
              {
                v17 = Length;
                String1.MaximumLength = Flink_low;
                Buffer = FullImageName->Buffer;
                String1.Length = Flink_low;
                String1.Buffer = &Buffer[(unsigned __int64)(v17 - Flink_low) >> 1];
                if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)v14, 1u) )
                {
                  ProcessImageName = PsLookupProcessByProcessId(ProcessId, (PEPROCESS *)&Object);
                  if ( ProcessImageName < 0 )
                  {
                    v20 = "Failed to lookup process [%x]";
                    v21 = 278;
                    goto LABEL_25;
                  }
                  ProcessImageName = SeLocateProcessImageName((PEPROCESS)Object, (PUNICODE_STRING *)&P);
                  if ( ProcessImageName >= 0 )
                  {
                    Pool2 = (struct _WORK_QUEUE_ITEM *)ExAllocatePool2(64, 56, 1836345667);
                    if ( !Pool2 )
                    {
                      AslLogCallPrintf(1, "CitmpLoadImageCallback", 298, "Out of memory");
                      goto LABEL_6;
                    }
                    if ( CurrentServerSilo )
                      ObfReferenceObject(CurrentServerSilo);
                    Pool2->Parameter = Pool2;
                    Pool2->WorkerRoutine = (PWORKER_THREAD_ROUTINE)CitmpLogUsageWorker;
                    Pool2[1].List.Blink = (struct _LIST_ENTRY *)P;
                    Pool2->List.Flink = 0;
                    Pool2[1].List.Flink = v14;
                    Pool2[1].WorkerRoutine = (PWORKER_THREAD_ROUTINE)CurrentServerSilo;
                    ExQueueWorkItem(Pool2, NormalWorkQueue);
                    P = 0;
                  }
                  else
                  {
                    v20 = "Failed to read process name [%x]";
                    v21 = 284;
LABEL_25:
                    AslLogCallPrintf(1, "CitmpLoadImageCallback", v21, v20, ProcessImageName);
LABEL_6:
                    if ( P )
                      ExFreePoolWithTag(P, 0);
                  }
                  if ( Object )
                    ObfDereferenceObject(Object);
                  return;
                }
                v11 = v23;
              }
            }
            if ( ++v12 >= *(_DWORD *)(v11 + 656) )
              goto LABEL_6;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140059f60  mov     rax, rsp
0x140059f63  push    rbx
0x140059f64  push    rsi
0x140059f65  push    r12
0x140059f67  push    r14
0x140059f69  push    r15
0x140059f6b  sub     rsp, 50h
0x140059f6f  xor     r12d, r12d
0x140059f72  mov     rbx, r8
0x140059f75  mov     [rax+20h], r12
0x140059f79  mov     r15, rdx
0x140059f7c  mov     [rax+8], r12
0x140059f80  mov     rsi, rcx
0x140059f83  mov     [rax-48h], r12
0x140059f87  call    cs:__imp_PsGetCurrentServerSilo
0x140059f8e  nop     dword ptr [rax+rax+00h]
0x140059f93  mov     edx, cs:g_AhcacheSiloContextSlot
0x140059f99  lea     r8, [rsp+78h+var_48]
0x140059f9e  mov     rcx, rax
0x140059fa1  mov     r14, rax
0x140059fa4  call    cs:__imp_PsGetPermanentSiloContext
0x140059fab  nop     dword ptr [rax+rax+00h]
0x140059fb0  mov     [rsp+78h+P], r12
0x140059fb8  mov     [rsp+78h+Object], r12
0x140059fc0  test    rsi, rsi
0x140059fc3  jz      loc_14005A052
0x140059fc9  test    r15, r15
0x140059fcc  jz      loc_14005A052
0x140059fd2  test    rbx, rbx
0x140059fd5  jz      short loc_14005A052
0x140059fd7  lea     rax, [rbx-8]
0x140059fdb  mov     [rsp+78h+arg_8], rbp
0x140059fe3  mov     [rsp+78h+arg_10], rdi
0x140059feb  test    rax, rax
0x140059fee  jnz     short loc_14005A060
0x140059ff0  lea     r9, aInvalidImagein; "Invalid ImageInfo, no IMAGE_INFO_EX fou"...
0x140059ff7  mov     r8d, 0E7h
0x140059ffd  lea     rdx, aCitmploadimage; "CitmpLoadImageCallback"
0x14005a004  mov     ecx, 1
0x14005a009  call    AslLogCallPrintf
0x14005a00e  mov     rcx, [rsp+78h+P]; P
0x14005a016  test    rcx, rcx
0x14005a019  jz      short loc_14005A029
0x14005a01b  xor     edx, edx; Tag
0x14005a01d  call    cs:__imp_ExFreePoolWithTag
0x14005a024  nop     dword ptr [rax+rax+00h]
0x14005a029  mov     rcx, [rsp+78h+Object]; Object
0x14005a031  test    rcx, rcx
0x14005a034  jz      short loc_14005A042
0x14005a036  call    cs:__imp_ObfDereferenceObject
0x14005a03d  nop     dword ptr [rax+rax+00h]
0x14005a042  mov     rbp, [rsp+78h+arg_8]
0x14005a04a  mov     rdi, [rsp+78h+arg_10]
0x14005a052  add     rsp, 50h
0x14005a056  pop     r15
0x14005a058  pop     r14
0x14005a05a  pop     r12
0x14005a05c  pop     rsi
0x14005a05d  pop     rbx
0x14005a05e  retn
0x14005a060  mov     rcx, [rax+30h]
0x14005a064  test    rcx, rcx
0x14005a067  jnz     short loc_14005A078
0x14005a069  lea     r9, aInvalidFileobj; "Invalid FileObject"
0x14005a070  mov     r8d, 0F1h
0x14005a076  jmp     short loc_140059FFD
0x14005a078  mov     rax, [rcx+10h]
0x14005a07c  test    rax, rax
0x14005a07f  jz      short loc_14005A042
0x14005a081  mov     rax, [rax+10h]
0x14005a085  test    rax, rax
0x14005a088  jz      short loc_14005A042
0x14005a08a  test    dword ptr [rax+30h], 200000h
0x14005a091  jz      short loc_14005A042
0x14005a093  mov     rcx, rsi
0x14005a096  call    CitmpComputeFileNameHash
0x14005a09b  mov     r8, [rsp+78h+var_48]
0x14005a0a0  mov     ebx, r12d
0x14005a0a3  mov     ebp, eax
0x14005a0a5  cmp     [r8+290h], ebx
0x14005a0ac  jbe     loc_14005A00E
0x14005a0b2  mov     ecx, ebx
0x14005a0b4  lea     rdx, [rcx+rcx*2]
0x14005a0b8  mov     rcx, [r8+288h]
0x14005a0bf  cmp     [rcx+rdx*8+10h], ebp
0x14005a0c3  lea     rdi, [rcx+rdx*8]
0x14005a0c7  jnz     short loc_14005A11B
0x14005a0c9  movzx   edx, word ptr [rdi]
0x14005a0cc  xorps   xmm0, xmm0
0x14005a0cf  movzx   eax, word ptr [rsi]
0x14005a0d2  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x14005a0d7  cmp     ax, dx
0x14005a0da  jb      short loc_14005A11B
0x14005a0dc  mov     ecx, eax
0x14005a0de  mov     [rsp+78h+String1.MaximumLength], dx
0x14005a0e3  mov     rax, [rsi+8]
0x14005a0e7  sub     rcx, rdx
0x14005a0ea  shr     rcx, 1
0x14005a0ed  mov     r8b, 1; CaseInSensitive
0x14005a0f0  mov     [rsp+78h+String1.Length], dx
0x14005a0f5  mov     rdx, rdi; String2
0x14005a0f8  lea     rcx, [rax+rcx*2]
0x14005a0fc  mov     [rsp+78h+String1.Buffer], rcx
0x14005a101  lea     rcx, [rsp+78h+String1]; String1
0x14005a106  call    cs:__imp_RtlEqualUnicodeString
0x14005a10d  nop     dword ptr [rax+rax+00h]
0x14005a112  test    al, al
0x14005a114  jnz     short loc_14005A12B
0x14005a116  mov     r8, [rsp+78h+var_48]
0x14005a11b  inc     ebx
0x14005a11d  cmp     ebx, [r8+290h]
0x14005a124  jb      short loc_14005A0B2
0x14005a126  jmp     loc_14005A00E
0x14005a12b  lea     rdx, [rsp+78h+Object]; Process
0x14005a133  mov     rcx, r15; ProcessId
0x14005a136  call    cs:__imp_PsLookupProcessByProcessId
0x14005a13d  nop     dword ptr [rax+rax+00h]
0x14005a142  test    eax, eax
0x14005a144  jns     short loc_14005A16D
0x14005a146  lea     r9, aFailedToLookup_0; "Failed to lookup process [%x]"
0x14005a14d  mov     r8d, 116h
0x14005a153  lea     rdx, aCitmploadimage; "CitmpLoadImageCallback"
0x14005a15a  mov     [rsp+78h+var_58], eax
0x14005a15e  mov     ecx, 1
0x14005a163  call    AslLogCallPrintf
0x14005a168  jmp     loc_14005A00E
0x14005a16d  mov     rcx, [rsp+78h+Object]; Process
0x14005a175  lea     rdx, [rsp+78h+P]; pImageFileName
0x14005a17d  call    cs:__imp_SeLocateProcessImageName
0x14005a184  nop     dword ptr [rax+rax+00h]
0x14005a189  test    eax, eax
0x14005a18b  jns     short loc_14005A19C
0x14005a18d  lea     r9, aFailedToReadPr; "Failed to read process name [%x]"
0x14005a194  mov     r8d, 11Ch
0x14005a19a  jmp     short loc_14005A153
0x14005a19c  mov     edx, 38h ; '8'
0x14005a1a1  mov     ecx, 40h ; '@'
0x14005a1a6  mov     r8d, 6D746943h
0x14005a1ac  call    cs:__imp_ExAllocatePool2
0x14005a1b3  nop     dword ptr [rax+rax+00h]
0x14005a1b8  mov     rbx, rax
0x14005a1bb  test    rax, rax
0x14005a1be  jnz     short loc_14005A1D2
0x14005a1c0  lea     r9, aOutOfMemory; "Out of memory"
0x14005a1c7  mov     r8d, 12Ah
0x14005a1cd  jmp     loc_140059FFD
0x14005a1d2  test    r14, r14
0x14005a1d5  jz      short loc_14005A1E6
0x14005a1d7  mov     rcx, r14; Object
0x14005a1da  call    cs:__imp_ObfReferenceObject
0x14005a1e1  nop     dword ptr [rax+rax+00h]
0x14005a1e6  lea     rax, CitmpLogUsageWorker
0x14005a1ed  mov     [rbx+18h], rbx
0x14005a1f1  mov     [rbx+10h], rax
0x14005a1f5  mov     edx, 3; QueueType
0x14005a1fa  mov     rax, [rsp+78h+P]
0x14005a202  mov     rcx, rbx; WorkItem
0x14005a205  mov     [rbx+28h], rax
0x14005a209  mov     [rbx], r12
0x14005a20c  mov     [rbx+20h], rdi
0x14005a210  mov     [rbx+30h], r14
0x14005a214  call    cs:__imp_ExQueueWorkItem
0x14005a21b  nop     dword ptr [rax+rax+00h]
0x14005a220  mov     [rsp+78h+P], r12
0x14005a228  jmp     loc_14005A029
```
