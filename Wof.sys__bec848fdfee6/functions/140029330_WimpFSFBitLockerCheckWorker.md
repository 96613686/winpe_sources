# WimpFSFBitLockerCheckWorker

- ea: `0x140029330`
- end: `0x1400295de`
- name: `WimpFSFBitLockerCheckWorker`
- size: `686`
- prototype: `LONG __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140029330`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002959c`
- `ntoskrnl!ZwClose` at `0x14002959c`
- `ntoskrnl!RtlCompareMemory` at `0x14002950e`
- `ntoskrnl!RtlCompareMemory` at `0x140029539`
- `ntoskrnl!RtlCompareMemory` at `0x14002950e`
- `ntoskrnl!RtlCompareMemory` at `0x140029539`
- `ntoskrnl!KeSetEvent` at `0x1400295b5`
- `ntoskrnl!KeSetEvent` at `0x1400295b5`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029401`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029499`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029401`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140029499`
- `ntoskrnl!ZwOpenFile` at `0x1400293ab`
- `ntoskrnl!ZwOpenFile` at `0x1400293ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029587`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029587`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029445`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029445`

## pseudocode

```c
LONG __fastcall WimpFSFBitLockerCheckWorker(__int64 a1)
{
  NTSTATUS v2; // ebx
  unsigned int *OutputBuffer; // rax
  unsigned int *v4; // rsi
  unsigned int v5; // r15d
  unsigned int *v6; // rdi
  unsigned int i; // r12d
  unsigned int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // rax
  struct _KEVENT *v11; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  SIZE_T NumberOfBytes; // [rsp+C0h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  ObjectAttributes.RootDirectory = 0;
  LODWORD(NumberOfBytes) = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 48);
  FileHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v2 >= 0 )
  {
    v2 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x4C4210CCu, 0, 0, &NumberOfBytes, 4u);
    if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147483643 )
    {
      if ( IoStatusBlock.Information >= 4 )
      {
        OutputBuffer = (unsigned int *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x69637077u);
        v4 = OutputBuffer;
        if ( OutputBuffer )
        {
          v2 = ZwDeviceIoControlFile(
                 FileHandle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 0x4C4210CCu,
                 0,
                 0,
                 OutputBuffer,
                 NumberOfBytes);
          if ( v2 >= 0 )
          {
            v5 = 8;
            v6 = v4 + 2;
            for ( i = 0; i < v4[1] && *v4 > v5; ++i )
            {
              v8 = v6[4];
              if ( v8 )
              {
                v9 = v6[5];
                if ( v9 )
                {
                  if ( v8 >= *v6 || v9 + v8 > *v6 )
                  {
                    v2 = -1073741675;
                    break;
                  }
                  if ( v6[3] == 6
                    && (RtlCompareMemory(L"SEI", (char *)v6 + v6[2], 6u) == 6
                     || v6[3] == 6 && RtlCompareMemory(L"HEI", (char *)v6 + v6[2], 6u) == 6) )
                  {
                    if ( v6[5] != 4 )
                    {
                      v2 = -1073741811;
                      break;
                    }
                    if ( (*(unsigned int *)((char *)v6 + v6[4]) & 4) != 0 )
                    {
                      *(_BYTE *)(a1 + 44) = 1;
                      break;
                    }
                  }
                }
              }
              v10 = *v6;
              v5 += v10;
              v6 = (unsigned int *)((char *)v6 + v10);
            }
          }
          ExFreePoolWithTag(v4, 0x69637077u);
        }
        else
        {
          v2 = -1073741801;
        }
      }
      else
      {
        v2 = -1073741811;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  v11 = *(struct _KEVENT **)(a1 + 32);
  *(_DWORD *)(a1 + 40) = v2;
  return KeSetEvent(v11, 0, 0);
}

```

## disassembly

```asm
0x140029330  mov     [rsp-8+arg_10], rbx
0x140029335  mov     [rsp-8+arg_18], rsi
0x14002933a  push    rbp
0x14002933b  push    rdi
0x14002933c  push    r12
0x14002933e  push    r14
0x140029340  push    r15
0x140029342  lea     rbp, [rsp-37h]
0x140029347  sub     rsp, 90h
0x14002934e  xor     eax, eax
0x140029350  mov     [rsp+0B0h+OpenOptions], 20h ; ' '; OpenOptions
0x140029358  xorps   xmm0, xmm0
0x14002935b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002935f  lea     rax, [rcx+30h]
0x140029363  mov     dword ptr [rbp+57h+NumberOfBytes], 0
0x14002936a  mov     r14, rcx
0x14002936d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140029371  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140029375  mov     [rbp+57h+FileHandle], 0
0x14002937d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140029381  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140029389  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002938d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140029395  mov     edx, 80h; DesiredAccess
0x14002939a  mov     [rsp+0B0h+ShareAccess], 3; ShareAccess
0x1400293a2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400293a6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400293ab  call    cs:__imp_ZwOpenFile
0x1400293b2  nop     dword ptr [rax+rax+00h]
0x1400293b7  mov     ebx, eax
0x1400293b9  test    eax, eax
0x1400293bb  js      loc_140029593
0x1400293c1  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400293c5  lea     rax, [rbp+57h+NumberOfBytes]
0x1400293c9  mov     [rsp+0B0h+OutputBufferLength], 4; OutputBufferLength
0x1400293d1  mov     edi, 4C4210CCh
0x1400293d6  mov     [rsp+0B0h+OutputBuffer], rax; OutputBuffer
0x1400293db  xor     r9d, r9d; ApcContext
0x1400293de  mov     [rsp+0B0h+InputBufferLength], 0; InputBufferLength
0x1400293e6  lea     rax, [rbp+57h+IoStatusBlock]
0x1400293ea  mov     [rsp+0B0h+InputBuffer], 0; InputBuffer
0x1400293f3  xor     r8d, r8d; ApcRoutine
0x1400293f6  mov     [rsp+0B0h+OpenOptions], edi; IoControlCode
0x1400293fa  xor     edx, edx; Event
0x1400293fc  mov     qword ptr [rsp+0B0h+ShareAccess], rax; IoStatusBlock
0x140029401  call    cs:__imp_ZwDeviceIoControlFile
0x140029408  nop     dword ptr [rax+rax+00h]
0x14002940d  mov     ecx, 80000000h
0x140029412  mov     ebx, eax
0x140029414  add     eax, ecx
0x140029416  test    ecx, eax
0x140029418  jnz     short loc_140029426
0x14002941a  cmp     ebx, 80000005h
0x140029420  jnz     loc_140029593
0x140029426  cmp     [rbp+57h+IoStatusBlock.Information], 4
0x14002942b  jnb     short loc_140029437
0x14002942d  mov     ebx, 0C000000Dh
0x140029432  jmp     loc_140029593
0x140029437  mov     edx, dword ptr [rbp+57h+NumberOfBytes]; NumberOfBytes
0x14002943a  mov     ecx, 1; PoolType
0x14002943f  mov     r8d, 69637077h; Tag
0x140029445  call    cs:__imp_ExAllocatePoolWithTag
0x14002944c  nop     dword ptr [rax+rax+00h]
0x140029451  mov     rsi, rax
0x140029454  test    rax, rax
0x140029457  jnz     short loc_140029463
0x140029459  mov     ebx, 0C0000017h
0x14002945e  jmp     loc_140029593
0x140029463  mov     eax, dword ptr [rbp+57h+NumberOfBytes]
0x140029466  xor     r9d, r9d; ApcContext
0x140029469  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002946d  xor     r8d, r8d; ApcRoutine
0x140029470  mov     [rsp+0B0h+OutputBufferLength], eax; OutputBufferLength
0x140029474  xor     edx, edx; Event
0x140029476  mov     [rsp+0B0h+OutputBuffer], rsi; OutputBuffer
0x14002947b  lea     rax, [rbp+57h+IoStatusBlock]
0x14002947f  mov     [rsp+0B0h+InputBufferLength], 0; InputBufferLength
0x140029487  mov     [rsp+0B0h+InputBuffer], 0; InputBuffer
0x140029490  mov     [rsp+0B0h+OpenOptions], edi; IoControlCode
0x140029494  mov     qword ptr [rsp+0B0h+ShareAccess], rax; IoStatusBlock
0x140029499  call    cs:__imp_ZwDeviceIoControlFile
0x1400294a0  nop     dword ptr [rax+rax+00h]
0x1400294a5  mov     ebx, eax
0x1400294a7  test    eax, eax
0x1400294a9  js      loc_14002957F
0x1400294af  mov     r15d, 8
0x1400294b5  lea     rdi, [rsi+8]
0x1400294b9  xor     r12d, r12d
0x1400294bc  cmp     r12d, [rsi+4]
0x1400294c0  jnb     loc_14002957F
0x1400294c6  cmp     [rsi], r15d
0x1400294c9  jbe     loc_14002957F
0x1400294cf  mov     eax, [rdi+10h]
0x1400294d2  test    eax, eax
0x1400294d4  jz      loc_14002955C
0x1400294da  mov     edx, [rdi+14h]
0x1400294dd  test    edx, edx
0x1400294df  jz      short loc_14002955C
0x1400294e1  mov     ecx, [rdi]
0x1400294e3  cmp     eax, ecx
0x1400294e5  jnb     loc_14002957A
0x1400294eb  add     eax, edx
0x1400294ed  cmp     eax, ecx
0x1400294ef  ja      loc_14002957A
0x1400294f5  cmp     dword ptr [rdi+0Ch], 6
0x1400294f9  jnz     short loc_14002955C
0x1400294fb  mov     edx, [rdi+8]
0x1400294fe  lea     rcx, aSei; "SEI"
0x140029505  add     rdx, rdi; Source2
0x140029508  mov     r8d, 6; Length
0x14002950e  call    cs:__imp_RtlCompareMemory
0x140029515  nop     dword ptr [rax+rax+00h]
0x14002951a  cmp     rax, 6
0x14002951e  jz      short loc_14002954B
0x140029520  cmp     dword ptr [rdi+0Ch], 6
0x140029524  jnz     short loc_14002955C
0x140029526  mov     edx, [rdi+8]
0x140029529  lea     rcx, aHei; "HEI"
0x140029530  add     rdx, rdi; Source2
0x140029533  mov     r8d, 6; Length
0x140029539  call    cs:__imp_RtlCompareMemory
0x140029540  nop     dword ptr [rax+rax+00h]
0x140029545  cmp     rax, 6
0x140029549  jnz     short loc_14002955C
0x14002954b  cmp     dword ptr [rdi+14h], 4
0x14002954f  jnz     short loc_140029573
0x140029551  mov     eax, [rdi+10h]
0x140029554  mov     ecx, [rax+rdi]
0x140029557  test    cl, 4
0x14002955a  jnz     short loc_14002956C
0x14002955c  mov     eax, [rdi]
0x14002955e  inc     r12d
0x140029561  add     r15d, eax
0x140029564  add     rdi, rax
0x140029567  jmp     loc_1400294BC
0x14002956c  mov     byte ptr [r14+2Ch], 1
0x140029571  jmp     short loc_14002957F
0x140029573  mov     ebx, 0C000000Dh
0x140029578  jmp     short loc_14002957F
0x14002957a  mov     ebx, 0C0000095h
0x14002957f  mov     edx, 69637077h; Tag
0x140029584  mov     rcx, rsi; P
0x140029587  call    cs:__imp_ExFreePoolWithTag
0x14002958e  nop     dword ptr [rax+rax+00h]
0x140029593  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140029597  test    rcx, rcx
0x14002959a  jz      short loc_1400295A8
0x14002959c  call    cs:__imp_ZwClose
0x1400295a3  nop     dword ptr [rax+rax+00h]
0x1400295a8  mov     rcx, [r14+20h]; Event
0x1400295ac  xor     r8d, r8d; Wait
0x1400295af  xor     edx, edx; Increment
0x1400295b1  mov     [r14+28h], ebx
0x1400295b5  call    cs:__imp_KeSetEvent
0x1400295bc  nop     dword ptr [rax+rax+00h]
0x1400295c1  lea     r11, [rsp+0B0h+var_20]
0x1400295c9  mov     rbx, [r11+40h]
0x1400295cd  mov     rsi, [r11+48h]
0x1400295d1  mov     rsp, r11
0x1400295d4  pop     r15
0x1400295d6  pop     r14
0x1400295d8  pop     r12
0x1400295da  pop     rdi
0x1400295db  pop     rbp
0x1400295dc  retn
```
