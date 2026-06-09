# BipTaskInstanceCreate

- ea: `0x18002ded0`
- end: `0x18002e0d9`
- name: `BipTaskInstanceCreate`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18002dbb0`

## callees

- `0x18002ded0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18002df6b`
- `ntdll!RtlInitializeSRWLock` at `0x18002df6b`
- `ntdll!RtlAllocateHeap` at `0x18002df42`
- `ntdll!RtlAllocateHeap` at `0x18002df42`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002e0b9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002e0b9`
- `RPCRT4!UuidCreate` at `0x18002df18`
- `RPCRT4!UuidCreate` at `0x18002df18`

## pseudocode

```c
__int64 __fastcall BipTaskInstanceCreate(__int64 a1, UUID *a2, int a3, _QWORD *a4)
{
  UUID *p_Uuid; // rsi
  RPC_STATUS v8; // eax
  unsigned int v9; // ebx
  _QWORD *Heap; // rax
  _QWORD *v11; // rbx
  __int128 v12; // xmm0
  _DWORD v14[2]; // [rsp+38h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-61h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-51h] BYREF
  __int128 v17; // [rsp+68h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-29h] BYREF
  char *v19; // [rsp+88h] [rbp-19h]
  int v20; // [rsp+90h] [rbp-11h]
  int v21; // [rsp+94h] [rbp-Dh]
  _DWORD *v22; // [rsp+98h] [rbp-9h]
  __int64 v23; // [rsp+A0h] [rbp-1h]
  __int128 *v24; // [rsp+A8h] [rbp+7h]
  __int64 v25; // [rsp+B0h] [rbp+Fh]
  UUID *v26; // [rsp+B8h] [rbp+17h]
  __int64 v27; // [rsp+C0h] [rbp+1Fh]

  p_Uuid = a2;
  Uuid = 0;
  if ( a2 || (p_Uuid = &Uuid, (v8 = UuidCreate(&Uuid)) == 0) || v8 == 1824 )
  {
    Heap = RtlAllocateHeap(BipHeap, 0, 0x208u);
    v11 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, 0x208u);
      RtlInitializeSRWLock(v11 + 6);
      v11[40] = -1;
      v11[41] = -1;
      *((_DWORD *)v11 + 125) = 3;
      v11[8] = a1;
      *((_DWORD *)v11 + 35) = a3;
      *(UUID *)v11 = *p_Uuid;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 28));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 72) + 28LL));
      *a4 = v11;
      v9 = 0;
    }
    else
    {
      v9 = -1073741801;
    }
  }
  else
  {
    v9 = -1073741693;
  }
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v12 = 0;
    if ( a1 )
      v12 = *(_OWORD *)(a1 + 32);
    v17 = v12;
    v24 = &v17;
    v14[0] = v9;
    v22 = v14;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v26 = p_Uuid;
    v27 = 16;
    v25 = 16;
    v23 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v19 = byte_1800AE915;
    UserData.Reserved = 2;
    v20 = 52;
    v21 = 1;
    v14[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return v9;
}

```

## disassembly

```asm
0x18002ded0  mov     r11, rsp
0x18002ded3  push    rbp
0x18002ded4  push    rbx
0x18002ded5  push    rsi
0x18002ded6  push    rdi
0x18002ded7  lea     rbp, [r11-5Fh]
0x18002dedb  sub     rsp, 0D8h
0x18002dee2  mov     rax, cs:__security_cookie
0x18002dee9  xor     rax, rsp
0x18002deec  mov     [rbp+57h+var_30], rax
0x18002def0  mov     [r11+10h], r14
0x18002def4  xorps   xmm0, xmm0
0x18002def7  mov     [r11-28h], r15
0x18002defb  mov     r15, r9
0x18002defe  mov     r14d, r8d
0x18002df01  mov     rsi, rdx
0x18002df04  mov     rdi, rcx
0x18002df07  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18002df0b  test    rdx, rdx
0x18002df0e  jnz     short loc_18002DF33
0x18002df10  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18002df14  lea     rsi, [rbp+57h+Uuid]
0x18002df18  call    cs:__imp_UuidCreate
0x18002df1e  test    eax, eax
0x18002df20  jz      short loc_18002DF33
0x18002df22  cmp     eax, 720h
0x18002df27  jz      short loc_18002DF33
0x18002df29  mov     ebx, 0C0000083h
0x18002df2e  jmp     loc_18002DFB3
0x18002df33  mov     rcx, cs:BipHeap; HeapHandle
0x18002df3a  xor     edx, edx; Flags
0x18002df3c  mov     r8d, 208h; Size
0x18002df42  call    cs:__imp_RtlAllocateHeap
0x18002df48  mov     rbx, rax
0x18002df4b  test    rax, rax
0x18002df4e  jnz     short loc_18002DF57
0x18002df50  mov     ebx, 0C0000017h
0x18002df55  jmp     short loc_18002DFB3
0x18002df57  xor     edx, edx; Val
0x18002df59  mov     r8d, 208h; Size
0x18002df5f  mov     rcx, rbx; void *
0x18002df62  call    memset_0
0x18002df67  lea     rcx, [rbx+30h]
0x18002df6b  call    cs:__imp_RtlInitializeSRWLock
0x18002df71  mov     qword ptr [rbx+140h], 0FFFFFFFFFFFFFFFFh
0x18002df7c  mov     qword ptr [rbx+148h], 0FFFFFFFFFFFFFFFFh
0x18002df87  mov     dword ptr [rbx+1F4h], 3
0x18002df91  mov     [rbx+40h], rdi
0x18002df95  mov     [rbx+8Ch], r14d
0x18002df9c  movups  xmm0, xmmword ptr [rsi]
0x18002df9f  movups  xmmword ptr [rbx], xmm0
0x18002dfa2  lock inc dword ptr [rdi+1Ch]
0x18002dfa6  mov     rax, [rdi+48h]
0x18002dfaa  lock inc dword ptr [rax+1Ch]
0x18002dfae  mov     [r15], rbx
0x18002dfb1  xor     ebx, ebx
0x18002dfb3  mov     eax, cs:dword_1800C3098
0x18002dfb9  mov     r15, [rsp+0D0h]
0x18002dfc1  mov     r14, [rsp+0F0h+arg_8]
0x18002dfc9  cmp     eax, 5
0x18002dfcc  jbe     loc_18002E0BF
0x18002dfd2  mov     rcx, cs:qword_1800C30B0
0x18002dfd9  mov     rax, cs:qword_1800C30A8
0x18002dfe0  test    al, 2
0x18002dfe2  jz      loc_18002E0BF
0x18002dfe8  mov     rax, rcx
0x18002dfeb  and     eax, 2
0x18002dfee  cmp     rax, rcx
0x18002dff1  jnz     loc_18002E0BF
0x18002dff7  xorps   xmm0, xmm0
0x18002dffa  test    rdi, rdi
0x18002dffd  jz      short loc_18002E003
0x18002dfff  movups  xmm0, xmmword ptr [rdi+20h]
0x18002e003  movdqa  [rbp+57h+var_90], xmm0
0x18002e008  lea     rax, [rbp+57h+var_90]
0x18002e00c  mov     [rbp+57h+var_50], rax
0x18002e010  lea     rcx, _TraceLoggingMetadataEnd
0x18002e017  lea     rax, [rbp+57h+var_C0]
0x18002e01b  mov     [rbp+57h+var_C0], ebx
0x18002e01e  mov     [rbp+57h+var_60], rax
0x18002e022  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002e026  movzx   eax, cs:word_1800AE90B
0x18002e02d  xor     r9d, r9d; RelatedActivityId
0x18002e030  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002e033  xor     r8d, r8d; ActivityId
0x18002e036  mov     rax, cs:off_1800C30A0
0x18002e03d  mov     [rbp+57h+UserData.Ptr], rax
0x18002e041  mov     [rbp+57h+var_40], rsi
0x18002e045  mov     [rbp+57h+var_38], 10h
0x18002e04d  mov     [rbp+57h+var_48], 10h
0x18002e055  mov     [rbp+57h+var_58], 4
0x18002e05d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002e064  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x18002e06c  movzx   eax, word ptr [rax]
0x18002e06f  mov     [rbp+57h+UserData.Size], eax
0x18002e072  lea     rax, byte_1800AE915
0x18002e079  mov     [rbp+57h+var_70], rax
0x18002e07d  lea     rax, _TraceLoggingMetadata
0x18002e084  sub     ecx, eax
0x18002e086  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x18002e08d  mov     [rbp+57h+var_68], 34h ; '4'
0x18002e094  lea     rax, [rbp+57h+UserData]
0x18002e098  mov     [rbp+57h+var_64], 1
0x18002e09f  mov     [rbp+57h+var_BC], ecx
0x18002e0a2  mov     ecx, [rbp+57h+var_BC]
0x18002e0a5  mov     rcx, cs:RegHandle; RegHandle
0x18002e0ac  mov     [rsp+28h], rax; UserData
0x18002e0b1  mov     [rsp+0F0h+UserDataCount], 5; UserDataCount
0x18002e0b9  call    cs:__imp_EventWriteTransfer
0x18002e0bf  mov     eax, ebx
0x18002e0c1  mov     rcx, [rbp+57h+var_30]
0x18002e0c5  xor     rcx, rsp; StackCookie
0x18002e0c8  call    __security_check_cookie
0x18002e0cd  add     rsp, 0D8h
0x18002e0d4  pop     rdi
0x18002e0d5  pop     rsi
0x18002e0d6  pop     rbx
0x18002e0d7  pop     rbp
0x18002e0d8  retn
```
