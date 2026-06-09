# VsmmProcessQueryMemoryHostingHandle

- ea: `0x1400a69e0`
- end: `0x1400a6bac`
- name: `VsmmProcessQueryMemoryHostingHandle`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14008ddc4`

## callees

- `0x14002f724`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400386a0`
- `0x1400a69e0`

## import_xrefs

- `ntoskrnl!PsProcessType` at `0x1400a6aeb`
- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x1400a6b30`
- `ntoskrnl!ObOpenObjectByPointerWithTag` at `0x1400a6b30`
- `ntoskrnl!ExGetPreviousMode` at `0x1400a6afe`
- `ntoskrnl!ExGetPreviousMode` at `0x1400a6afe`
- `ntoskrnl!NtClose` at `0x1400a6b70`
- `ntoskrnl!NtClose` at `0x1400a6b70`

## pseudocode

```c
__int64 __fastcall VsmmProcessQueryMemoryHostingHandle(
        __int64 a1,
        ACCESS_MASK *a2,
        int a3,
        HANDLE *a4,
        int a5,
        _DWORD *a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rbp
  ACCESS_MASK v11; // edi
  void *v12; // rsi
  KPROCESSOR_MODE AccessMode; // al
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF

  Handle = 0;
  if ( a2 )
  {
    if ( a3 == 4 )
    {
      if ( a4 )
      {
        if ( a5 == 8 )
        {
          v10 = a1 + 10256;
          VidObjectLockAcquireShared(a1 + 10256);
          if ( *(_QWORD *)(a1 + 10328) )
          {
            v11 = *a2;
            v12 = *(void **)(a1 + 10328);
            AccessMode = ExGetPreviousMode();
            v9 = ObOpenObjectByPointerWithTag(
                   v12,
                   0,
                   0,
                   v11,
                   (POBJECT_TYPE)PsProcessType,
                   AccessMode,
                   0x6D4D6456u,
                   &Handle);
            VidObjectLockRelease(v10);
            if ( (v9 & 0x80000000) == 0 )
            {
              v9 = 0;
              *a4 = Handle;
              *a6 = 8;
              return v9;
            }
            VidTraceErrorStatusInternal0(
              "VsmmProcessQueryMemoryHostingHandle",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
              496,
              v9);
          }
          else
          {
            v9 = -1073741811;
            VidTraceErrorInternal0(
              "VsmmProcessQueryMemoryHostingHandle",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
              477);
            VidObjectLockRelease(v10);
          }
        }
        else
        {
          v9 = -1073741811;
          VidTraceErrorInternal0(
            "VsmmProcessQueryMemoryHostingHandle",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c",
            463);
        }
      }
      else
      {
        v9 = -1073741811;
        VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 456);
      }
    }
    else
    {
      v9 = -1073741811;
      VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 449);
    }
  }
  else
  {
    v9 = -1073741811;
    VidTraceErrorInternal0("VsmmProcessQueryMemoryHostingHandle", "onecore\\vm\\vid\\sys\\vsmm\\vsmmprocess.c", 438);
  }
  if ( Handle )
    NtClose(Handle);
  return v9;
}

```

## disassembly

```asm
0x1400a69e0  mov     [rsp+arg_0], rbx
0x1400a69e5  mov     [rsp+arg_10], rbp
0x1400a69ea  push    rsi
0x1400a69eb  push    rdi
0x1400a69ec  push    r14
0x1400a69ee  sub     rsp, 40h
0x1400a69f2  mov     [rsp+58h+arg_8], 0
0x1400a69fb  mov     r14, r9
0x1400a69fe  mov     rdi, rdx
0x1400a6a01  mov     rsi, rcx
0x1400a6a04  test    rdx, rdx
0x1400a6a07  jnz     short loc_1400A6A2C
0x1400a6a09  mov     ebx, 0C000000Dh
0x1400a6a0e  mov     r8d, 1B6h
0x1400a6a14  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6a1b  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6a22  call    VidTraceErrorInternal0
0x1400a6a27  jmp     loc_1400A6B66
0x1400a6a2c  cmp     r8d, 4
0x1400a6a30  jz      short loc_1400A6A55
0x1400a6a32  mov     ebx, 0C000000Dh
0x1400a6a37  mov     r8d, 1C1h
0x1400a6a3d  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6a44  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6a4b  call    VidTraceErrorInternal0
0x1400a6a50  jmp     loc_1400A6B66
0x1400a6a55  test    r14, r14
0x1400a6a58  jnz     short loc_1400A6A7D
0x1400a6a5a  mov     ebx, 0C000000Dh
0x1400a6a5f  mov     r8d, 1C8h
0x1400a6a65  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6a6c  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6a73  call    VidTraceErrorInternal0
0x1400a6a78  jmp     loc_1400A6B66
0x1400a6a7d  cmp     [rsp+58h+arg_20], 8
0x1400a6a85  jz      short loc_1400A6AAA
0x1400a6a87  mov     ebx, 0C000000Dh
0x1400a6a8c  mov     r8d, 1CFh
0x1400a6a92  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6a99  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6aa0  call    VidTraceErrorInternal0
0x1400a6aa5  jmp     loc_1400A6B66
0x1400a6aaa  lea     rbp, [rcx+2810h]
0x1400a6ab1  mov     rcx, rbp
0x1400a6ab4  call    VidObjectLockAcquireShared
0x1400a6ab9  cmp     qword ptr [rsi+2858h], 0
0x1400a6ac1  jnz     short loc_1400A6AEB
0x1400a6ac3  mov     ebx, 0C000000Dh
0x1400a6ac8  mov     r8d, 1DDh
0x1400a6ace  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6ad5  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6adc  call    VidTraceErrorInternal0
0x1400a6ae1  mov     rcx, rbp
0x1400a6ae4  call    VidObjectLockRelease
0x1400a6ae9  jmp     short loc_1400A6B66
0x1400a6aeb  mov     rax, cs:__imp_PsProcessType
0x1400a6af2  mov     edi, [rdi]
0x1400a6af4  mov     rsi, [rsi+2858h]
0x1400a6afb  mov     rbx, [rax]
0x1400a6afe  call    cs:__imp_ExGetPreviousMode
0x1400a6b05  nop     dword ptr [rax+rax+00h]
0x1400a6b0a  lea     rcx, [rsp+58h+arg_8]
0x1400a6b0f  mov     r9d, edi; DesiredAccess
0x1400a6b12  mov     [rsp+58h+Handle], rcx; Handle
0x1400a6b17  xor     r8d, r8d; PassedAccessState
0x1400a6b1a  mov     [rsp+58h+Tag], 6D4D6456h; Tag
0x1400a6b22  xor     edx, edx; HandleAttributes
0x1400a6b24  mov     [rsp+58h+AccessMode], al; AccessMode
0x1400a6b28  mov     rcx, rsi; Object
0x1400a6b2b  mov     [rsp+58h+ObjectType], rbx; ObjectType
0x1400a6b30  call    cs:__imp_ObOpenObjectByPointerWithTag
0x1400a6b37  nop     dword ptr [rax+rax+00h]
0x1400a6b3c  mov     rcx, rbp
0x1400a6b3f  mov     ebx, eax
0x1400a6b41  call    VidObjectLockRelease
0x1400a6b46  test    ebx, ebx
0x1400a6b48  jns     short loc_1400A6B7E
0x1400a6b4a  mov     r9d, ebx
0x1400a6b4d  lea     rdx, aOnecoreVmVidSy; "onecore\\vm\\vid\\sys\\vsmm\\vsmmproces"...
0x1400a6b54  mov     r8d, 1F0h
0x1400a6b5a  lea     rcx, aVsmmprocessque; "VsmmProcessQueryMemoryHostingHandle"
0x1400a6b61  call    VidTraceErrorStatusInternal0
0x1400a6b66  mov     rcx, [rsp+58h+arg_8]; Handle
0x1400a6b6b  test    rcx, rcx
0x1400a6b6e  jz      short loc_1400A6B96
0x1400a6b70  call    cs:__imp_NtClose
0x1400a6b77  nop     dword ptr [rax+rax+00h]
0x1400a6b7c  jmp     short loc_1400A6B96
0x1400a6b7e  mov     rax, [rsp+58h+arg_8]
0x1400a6b83  xor     ebx, ebx
0x1400a6b85  mov     [r14], rax
0x1400a6b88  mov     rax, [rsp+58h+arg_28]
0x1400a6b90  mov     dword ptr [rax], 8
0x1400a6b96  mov     rbp, [rsp+58h+arg_10]
0x1400a6b9b  mov     eax, ebx
0x1400a6b9d  mov     rbx, [rsp+58h+arg_0]
0x1400a6ba2  add     rsp, 40h
0x1400a6ba6  pop     r14
0x1400a6ba8  pop     rdi
0x1400a6ba9  pop     rsi
0x1400a6baa  retn
```
