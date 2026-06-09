# AhcProbeAndReadCommandLine

- ea: `0x1400278dc`
- end: `0x1400279d3`
- name: `AhcProbeAndReadCommandLine`
- size: `247`
- prototype: `__int64 __fastcall(void *Src, size_t Size, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004c3a0`

## callees

- `0x1400045b0`
- `0x140007b40`
- `0x1400278dc`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x14002793d`
- `ntoskrnl!MmIsUserAddress` at `0x14002793d`
- `ntoskrnl!ProbeForRead` at `0x14002790a`
- `ntoskrnl!ProbeForRead` at `0x14002790a`

## string_xrefs

- `0x14002797b`: `Exception reading command line [%x]`
- `0x140027988`: `AhcProbeAndReadCommandLine`

## pseudocode

```c
__int64 __fastcall AhcProbeAndReadCommandLine(void *Src, size_t Size, _QWORD *a3)
{
  size_t v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rbx
  int v9; // esi

  v5 = (unsigned int)Size;
  ProbeForRead(Src, (unsigned int)Size, 1u);
  v8 = (void *)AslAlloc(v6, v5 + 2, 1);
  if ( v8 )
  {
    if ( (unsigned __int8)MmIsUserAddress(Src) )
      RtlCopyFromUser(v8, Src, v5);
    else
      memmove(v8, Src, v5);
    *((_WORD *)v8 + (v5 >> 1)) = 0;
    v9 = 0;
  }
  else
  {
    v9 = -1073741801;
  }
  if ( v9 >= 0 )
  {
    *a3 = v8;
    v8 = 0;
  }
  if ( v8 )
    AslFree(v7, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400278dc  mov     rax, rsp
0x1400278df  mov     [rax+8], rbx
0x1400278e3  mov     [rax+10h], rsi
0x1400278e7  mov     [rax+18h], r8
0x1400278eb  push    rdi
0x1400278ec  push    r14
0x1400278ee  push    r15
0x1400278f0  sub     rsp, 40h
0x1400278f4  mov     r15, r8
0x1400278f7  mov     r14, rcx
0x1400278fa  xor     edi, edi
0x1400278fc  mov     [rax-20h], rdi
0x140027900  mov     esi, edx
0x140027902  lea     ebx, [rdi+1]
0x140027905  mov     r8d, ebx; Alignment
0x140027908  mov     edx, edx; Length
0x14002790a  call    cs:__imp_ProbeForRead
0x140027911  nop     dword ptr [rax+rax+00h]
0x140027916  lea     rdx, [rsi+2]
0x14002791a  mov     r8d, ebx
0x14002791d  call    AslAlloc
0x140027922  mov     rbx, rax
0x140027925  mov     [rsp+58h+var_20], rax
0x14002792a  test    rax, rax
0x14002792d  jnz     short loc_14002793A
0x14002792f  mov     esi, 0C0000017h
0x140027934  mov     [rsp+58h+var_28], esi
0x140027938  jmp     short loc_14002796F
0x14002793a  mov     rcx, r14
0x14002793d  call    cs:__imp_MmIsUserAddress
0x140027944  nop     dword ptr [rax+rax+00h]
0x140027949  mov     r8, rsi; Size
0x14002794c  mov     rdx, r14; Src
0x14002794f  mov     rcx, rbx; void *
0x140027952  test    al, al
0x140027954  jz      short loc_14002795D
0x140027956  call    RtlCopyFromUser
0x14002795b  jmp     short loc_140027962
0x14002795d  call    memmove
0x140027962  shr     rsi, 1
0x140027965  mov     [rbx+rsi*2], di
0x140027969  mov     esi, edi
0x14002796b  mov     [rsp+58h+var_28], edi
0x14002796f  jmp     short loc_1400279A5
0x140027971  mov     esi, eax
0x140027973  mov     [rsp+58h+var_28], eax
0x140027977  mov     [rsp+58h+var_38], eax
0x14002797b  lea     r9, aExceptionReadi; "Exception reading command line [%x]"
0x140027982  mov     r8d, 4E2h
0x140027988  lea     rdx, aAhcprobeandrea_0; "AhcProbeAndReadCommandLine"
0x14002798f  mov     ecx, 1
0x140027994  call    AslLogCallPrintf
0x140027999  xor     edi, edi
0x14002799b  mov     r15, [rsp+58h+arg_10]
0x1400279a0  mov     rbx, [rsp+58h+var_20]
0x1400279a5  test    esi, esi
0x1400279a7  js      short loc_1400279AF
0x1400279a9  mov     [r15], rbx
0x1400279ac  mov     rbx, rdi
0x1400279af  test    rbx, rbx
0x1400279b2  jz      short loc_1400279BC
0x1400279b4  mov     rdx, rbx
0x1400279b7  call    AslFree
0x1400279bc  mov     eax, esi
0x1400279be  mov     rbx, [rsp+58h+arg_0]
0x1400279c3  mov     rsi, [rsp+58h+arg_8]
0x1400279c8  add     rsp, 40h
0x1400279cc  pop     r15
0x1400279ce  pop     r14
0x1400279d0  pop     rdi
0x1400279d1  retn
```
