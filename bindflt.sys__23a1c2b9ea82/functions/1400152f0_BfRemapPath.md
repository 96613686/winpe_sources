# BfRemapPath

- ea: `0x1400152f0`
- end: `0x1400154a2`
- name: `BfRemapPath`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140013864`
- `0x140014324`

## callees

- `0x140001348`
- `0x140001fd0`
- `0x140002e0c`
- `0x1400152f0`
- `0x1400154b0`
- `0x1400172f0`
- `0x140017bf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015371`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015371`

## pseudocode

```c
__int64 __fastcall BfRemapPath(
        __int64 a1,
        __int16 *a2,
        struct _FLT_INSTANCE *a3,
        const UNICODE_STRING *a4,
        UNICODE_STRING *a5)
{
  char v9; // di
  int v10; // edx
  int Substring; // ebx
  int v12; // edx
  int v14; // r9d
  char v15; // [rsp+30h] [rbp-68h]
  __int64 v16; // [rsp+38h] [rbp-60h]
  int v17; // [rsp+38h] [rbp-60h]
  char v18; // [rsp+40h] [rbp-58h]
  struct _UNICODE_STRING P; // [rsp+50h] [rbp-48h] BYREF

  P = 0;
  v9 = 0;
  Substring = BfFormatPathFromFileNameInfo(a1, 0, &P, (__int64)a4);
  if ( Substring < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_4;
    v18 = Substring;
    v16 = a1 + 8;
    v14 = 85;
    v15 = -96;
    goto LABEL_15;
  }
  Substring = BfReplaceFirstSubstring(&P.Length, a2, a4, a5);
  if ( Substring < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = Substring;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        8,
        86,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        168,
        v17);
    }
  }
  else
  {
    Substring = BfPrependVolumeNameFromInstance(a3, a5);
    if ( Substring < 0 )
    {
      v9 = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = Substring;
        v14 = 87;
        v16 = (__int64)a5;
        v15 = -77;
LABEL_15:
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sDZd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          8,
          v14,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          v15,
          v16,
          v18);
      }
    }
  }
LABEL_4:
  if ( P.Buffer )
  {
    ExFreePoolWithTag(P.Buffer, 0x74734642u);
    P.Buffer = 0;
  }
  *(_DWORD *)&P.Length = 0;
  if ( v9 )
    BfFreeUnicodeString(a5);
  return (unsigned int)Substring;
}

```

## disassembly

```asm
0x1400152f0  push    rbx
0x1400152f2  push    rbp
0x1400152f3  push    rsi
0x1400152f4  push    rdi
0x1400152f5  push    r13
0x1400152f7  push    r14
0x1400152f9  push    r15
0x1400152fb  sub     rsp, 60h
0x1400152ff  mov     rbp, r8
0x140015302  mov     r15, rdx
0x140015305  xorps   xmm0, xmm0
0x140015308  lea     r8, [rsp+98h+P]
0x14001530d  xor     edx, edx
0x14001530f  mov     r14, r9
0x140015312  movups  xmmword ptr [rsp+98h+P.Length], xmm0
0x140015317  mov     r13, rcx
0x14001531a  xor     dil, dil
0x14001531d  call    BfFormatPathFromFileNameInfo
0x140015322  mov     rsi, [rsp+98h+arg_20]
0x14001532a  mov     ebx, eax
0x14001532c  test    eax, eax
0x14001532e  js      short loc_1400153A7
0x140015330  mov     r9, rsi
0x140015333  lea     rcx, [rsp+98h+P]
0x140015338  mov     r8, r14
0x14001533b  mov     rdx, r15
0x14001533e  call    BfReplaceFirstSubstring
0x140015343  mov     ebx, eax
0x140015345  test    eax, eax
0x140015347  js      loc_1400153D7
0x14001534d  mov     rdx, rsi
0x140015350  mov     rcx, rbp
0x140015353  call    BfPrependVolumeNameFromInstance
0x140015358  mov     ebx, eax
0x14001535a  test    eax, eax
0x14001535c  js      loc_140015432
0x140015362  mov     rcx, [rsp+98h+P.Buffer]; P
0x140015367  test    rcx, rcx
0x14001536a  jz      short loc_140015386
0x14001536c  mov     edx, 74734642h; Tag
0x140015371  call    cs:__imp_ExFreePoolWithTag
0x140015378  nop     dword ptr [rax+rax+00h]
0x14001537d  mov     [rsp+98h+P.Buffer], 0
0x140015386  xor     eax, eax
0x140015388  mov     dword ptr [rsp+98h+P.Length], eax
0x14001538c  test    dil, dil
0x14001538f  jnz     loc_140015495
0x140015395  mov     eax, ebx
0x140015397  add     rsp, 60h
0x14001539b  pop     r15
0x14001539d  pop     r14
0x14001539f  pop     r13
0x1400153a1  pop     rdi
0x1400153a2  pop     rsi
0x1400153a3  pop     rbp
0x1400153a4  pop     rbx
0x1400153a5  retn
0x1400153a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400153ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400153b5  jz      short loc_140015362
0x1400153b7  mov     dword ptr [rsp+98h+var_58], ebx
0x1400153bb  lea     rax, [r13+8]
0x1400153bf  mov     [rsp+98h+var_60], rax
0x1400153c4  mov     r9d, 55h ; 'U'
0x1400153ca  mov     dword ptr [rsp+98h+var_68], 0EA0h
0x1400153d2  jmp     loc_140015460
0x1400153d7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400153de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400153e5  jz      loc_140015362
0x1400153eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153f2  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400153f9  mov     dword ptr [rsp+98h+var_60], ebx
0x1400153fd  mov     r9d, 56h ; 'V'
0x140015403  mov     dword ptr [rsp+98h+var_68], 0EA8h
0x14001540b  mov     r8d, 8
0x140015411  mov     [rsp+98h+var_70], rax
0x140015416  mov     dl, 2
0x140015418  mov     rcx, [rcx+40h]
0x14001541c  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140015423  mov     [rsp+98h+var_78], rax
0x140015428  call    WPP_RECORDER_SF_sDd
0x14001542d  jmp     loc_140015362
0x140015432  mov     dil, 1
0x140015435  lea     rax, WPP_RECORDER_INITIALIZED
0x14001543c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015443  jz      loc_140015362
0x140015449  mov     dword ptr [rsp+98h+var_58], ebx
0x14001544d  mov     r9d, 57h ; 'W'
0x140015453  mov     [rsp+98h+var_60], rsi
0x140015458  mov     dword ptr [rsp+98h+var_68], 0EB3h
0x140015460  mov     rcx, cs:WPP_GLOBAL_Control
0x140015467  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001546e  mov     [rsp+98h+var_70], rax
0x140015473  mov     r8d, 8
0x140015479  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140015480  mov     dl, 2
0x140015482  mov     [rsp+98h+var_78], rax
0x140015487  mov     rcx, [rcx+40h]
0x14001548b  call    WPP_RECORDER_SF_sDZd
0x140015490  jmp     loc_140015362
0x140015495  mov     rcx, rsi
0x140015498  call    BfFreeUnicodeString
0x14001549d  jmp     loc_140015395
```
