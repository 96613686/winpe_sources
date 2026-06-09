# TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006dd8`
- end: `0x180006e79`
- name: `?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ`
- size: `161`
- prototype: `void(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001395f`
- `0x180013995`

## callees

- `0x180006dd8`
- `0x18000d998`
- `0x18000dc8c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006e14`
- `msvcrt!_vsnwprintf` at `0x180006e14`

## string_xrefs

- `0x180006e59`: `com\complus\dtc\inc\tracedstrsafe.h`

## pseudocode

```c
void TracedStringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  int v4; // ecx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_13:
    TraceFile(v4, "failed in TracedStringCchPrintfW", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 119);
    DtcInternalErrorW(L"failed in TracedStringCchPrintfW");
  }
  if ( a2 > 0x7FFFFFFF )
  {
    v4 = -2147024809;
    *a1 = 0;
    goto LABEL_13;
  }
  v5 = a2 - 1;
  v6 = _vsnwprintf(a1, a2 - 1, a3, va);
  if ( v6 < 0 || v6 > v5 )
  {
    v4 = -2147024774;
  }
  else
  {
    v4 = 0;
    if ( v6 != v5 )
      goto LABEL_10;
  }
  a1[v5] = 0;
LABEL_10:
  if ( v4 < 0 )
    goto LABEL_13;
}

```

## disassembly

```asm
0x180006dd8  mov     rax, rsp
0x180006ddb  mov     [rax+18h], r8
0x180006ddf  mov     [rax+20h], r9
0x180006de3  push    rbx
0x180006de4  push    rdi
0x180006de5  sub     rsp, 38h
0x180006de9  mov     qword ptr [rax-28h], 0
0x180006df1  mov     rdi, rcx
0x180006df4  lea     r9, [rax+20h]; Args
0x180006df8  test    rdx, rdx
0x180006dfb  jz      short loc_180006E44
0x180006dfd  cmp     rdx, 7FFFFFFFh
0x180006e04  jbe     short loc_180006E0D
0x180006e06  mov     ecx, 80070057h; Buffer
0x180006e0b  jmp     short loc_180006E4E
0x180006e0d  lea     rbx, [rdx-1]
0x180006e11  mov     rdx, rbx; BufferCount
0x180006e14  call    cs:__imp__vsnwprintf
0x180006e1a  test    eax, eax
0x180006e1c  js      short loc_180006E2E
0x180006e1e  cdqe
0x180006e20  cmp     rax, rbx
0x180006e23  ja      short loc_180006E2E
0x180006e25  xor     ecx, ecx
0x180006e27  cmp     rax, rbx
0x180006e2a  jnz     short loc_180006E39
0x180006e2c  jmp     short loc_180006E33
0x180006e2e  mov     ecx, 8007007Ah
0x180006e33  xor     eax, eax
0x180006e35  mov     [rdi+rbx*2], ax
0x180006e39  test    ecx, ecx
0x180006e3b  js      short loc_180006E53
0x180006e3d  add     rsp, 38h
0x180006e41  pop     rdi
0x180006e42  pop     rbx
0x180006e43  retn
0x180006e44  mov     ecx, 80070057h; int
0x180006e49  test    rdx, rdx
0x180006e4c  jz      short loc_180006E53
0x180006e4e  xor     eax, eax
0x180006e50  mov     [rdi], ax
0x180006e53  mov     r9d, 77h ; 'w'; unsigned int
0x180006e59  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x180006e60  lea     rdx, aFailedInTraced; "failed in TracedStringCchPrintfW"
0x180006e67  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006e6c  lea     rcx, aFailedInTraced_5; "failed in TracedStringCchPrintfW"
0x180006e73  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
