# EdpGetLogFullPathFromRelativePath

- ea: `0x14002dfcc`
- end: `0x14002e106`
- name: `EdpGetLogFullPathFromRelativePath`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002ba70`

## callees

- `0x140005af0`
- `0x14002dfcc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e067`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e067`
- `ntoskrnl!ExAllocatePool2` at `0x14002e026`
- `ntoskrnl!ExAllocatePool2` at `0x14002e026`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14002dfdc`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14002dfdc`

## string_xrefs

- `0x14002e0e8`: `\security\EDP\Logs\AppLearning_1.etl`

## pseudocode

```c
__int64 __fastcall EdpGetLogFullPathFromRelativePath(__int64 a1, wchar_t **a2, __int64 a3, __int64 a4)
{
  __int64 NtSystemRoot; // rax
  __int64 v6; // r9
  __int64 v7; // rcx
  const wchar_t *v8; // rbx
  unsigned int v9; // esi
  size_t *v10; // r8
  wchar_t *Pool2; // r11
  NTSTATUS v12; // ebx
  size_t v13; // rdi
  size_t *v15; // r8
  unsigned __int64 v16; // rcx
  wchar_t *v17; // rax
  size_t v18; // rdx
  size_t cchToCopy; // [rsp+20h] [rbp-48h]
  __int64 v20; // [rsp+28h] [rbp-40h]

  NtSystemRoot = RtlGetNtSystemRoot(a1, a2, a3, a4, cchToCopy, v20);
  v7 = -1;
  v8 = (const wchar_t *)NtSystemRoot;
  do
    ++v7;
  while ( *(_WORD *)(NtSystemRoot + 2 * v7) );
  v9 = (unsigned __int16)(2 * (v7 + 1)) - 2;
  Pool2 = (wchar_t *)ExAllocatePool2(256, 2LL * (v9 + 1) + 74, 1097884741, v6);
  if ( Pool2 )
  {
    v13 = (2 * (unsigned __int64)(v9 + 1) + 74) >> 1;
    if ( v13 - 1 <= 0x7FFFFFFE )
    {
      if ( v9 <= 0x7FFFFFFEuLL )
      {
        v12 = RtlStringCopyWorkerW(Pool2, v13, v10, v8, v9);
        if ( v12 >= 0 )
        {
          v16 = (2 * (unsigned __int64)(v9 + 1) + 74) >> 1;
          v17 = Pool2;
          do
          {
            if ( !*v17 )
              break;
            ++v17;
            --v16;
          }
          while ( v16 );
          v12 = v16 == 0 ? 0xC000000D : 0;
          v18 = v16 ? v13 - v16 : 0LL;
          if ( v16 )
          {
            v12 = RtlStringCopyWorkerW(&Pool2[v18], v13 - v18, v15, L"\\security\\EDP\\Logs\\AppLearning_1.etl", 0x25u);
            if ( v12 >= 0 )
            {
              *a2 = Pool2;
              return (unsigned int)v12;
            }
          }
        }
        goto LABEL_9;
      }
      *Pool2 = 0;
    }
    v12 = -1073741811;
LABEL_9:
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)v12;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x14002dfcc  push    rbx
0x14002dfce  push    rbp
0x14002dfcf  push    rsi
0x14002dfd0  push    rdi
0x14002dfd1  push    r14
0x14002dfd3  push    r15
0x14002dfd5  sub     rsp, 38h
0x14002dfd9  mov     r14, rdx
0x14002dfdc  call    cs:__imp_RtlGetNtSystemRoot
0x14002dfe3  nop     dword ptr [rax+rax+00h]
0x14002dfe8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002dfec  mov     rbx, rax
0x14002dfef  xor     ebp, ebp
0x14002dff1  inc     rcx
0x14002dff4  cmp     [rax+rcx*2], bp
0x14002dff8  jnz     short loc_14002DFF1
0x14002dffa  mov     r15d, 1
0x14002e000  mov     r8d, 41706445h
0x14002e006  add     cx, r15w
0x14002e00a  add     cx, cx
0x14002e00d  movzx   esi, cx
0x14002e010  mov     ecx, 100h
0x14002e015  add     esi, 0FFFFFFFEh
0x14002e018  lea     eax, [rsi+1]
0x14002e01b  lea     rdi, ds:4Ah[rax*2]
0x14002e023  mov     rdx, rdi
0x14002e026  call    cs:__imp_ExAllocatePool2
0x14002e02d  nop     dword ptr [rax+rax+00h]
0x14002e032  mov     r11, rax
0x14002e035  test    rax, rax
0x14002e038  jnz     short loc_14002E041
0x14002e03a  mov     ebx, 0C0000017h
0x14002e03f  jmp     short loc_14002E073
0x14002e041  shr     rdi, 1
0x14002e044  mov     ecx, 7FFFFFFEh
0x14002e049  lea     rax, [rdi-1]
0x14002e04d  cmp     rax, rcx
0x14002e050  ja      short loc_14002E05D
0x14002e052  mov     eax, esi
0x14002e054  cmp     rax, rcx
0x14002e057  jbe     short loc_14002E083
0x14002e059  mov     [r11], bp
0x14002e05d  mov     ebx, 0C000000Dh
0x14002e062  xor     edx, edx; Tag
0x14002e064  mov     rcx, r11; P
0x14002e067  call    cs:__imp_ExFreePoolWithTag
0x14002e06e  nop     dword ptr [rax+rax+00h]
0x14002e073  mov     eax, ebx
0x14002e075  add     rsp, 38h
0x14002e079  pop     r15
0x14002e07b  pop     r14
0x14002e07d  pop     rdi
0x14002e07e  pop     rsi
0x14002e07f  pop     rbp
0x14002e080  pop     rbx
0x14002e081  retn
0x14002e083  mov     r9, rbx; pszSrc
0x14002e086  mov     [rsp+68h+cchToCopy], rax; cchToCopy
0x14002e08b  mov     rdx, rdi; cchDest
0x14002e08e  mov     rcx, r11; pszDest
0x14002e091  call    RtlStringCopyWorkerW
0x14002e096  mov     ebx, eax
0x14002e098  test    eax, eax
0x14002e09a  js      short loc_14002E062
0x14002e09c  mov     rcx, rdi
0x14002e09f  mov     rax, r11
0x14002e0a2  mov     rdx, rdi
0x14002e0a5  cmp     [rax], bp
0x14002e0a8  jz      short loc_14002E0B3
0x14002e0aa  add     rax, 2
0x14002e0ae  sub     rcx, r15
0x14002e0b1  jnz     short loc_14002E0A5
0x14002e0b3  mov     rax, rcx
0x14002e0b6  neg     rax
0x14002e0b9  sbb     ebx, ebx
0x14002e0bb  not     ebx
0x14002e0bd  and     ebx, 0C000000Dh
0x14002e0c3  test    rcx, rcx
0x14002e0c6  jz      short loc_14002E0CD
0x14002e0c8  sub     rdx, rcx
0x14002e0cb  jmp     short loc_14002E0D0
0x14002e0cd  mov     rdx, rbp
0x14002e0d0  test    rcx, rcx
0x14002e0d3  jz      short loc_14002E062
0x14002e0d5  sub     rdi, rdx
0x14002e0d8  mov     [rsp+68h+cchToCopy], 25h ; '%'; cchToCopy
0x14002e0e1  lea     rcx, [r11+rdx*2]; pszDest
0x14002e0e5  mov     rdx, rdi; cchDest
0x14002e0e8  lea     r9, EDP_APP_LEARNING_LOG_PATH; "\\security\\EDP\\Logs\\AppLearning_1.et"...
0x14002e0ef  call    RtlStringCopyWorkerW
0x14002e0f4  mov     ebx, eax
0x14002e0f6  test    eax, eax
0x14002e0f8  js      loc_14002E062
0x14002e0fe  mov     [r14], r11
0x14002e101  jmp     loc_14002E073
```
