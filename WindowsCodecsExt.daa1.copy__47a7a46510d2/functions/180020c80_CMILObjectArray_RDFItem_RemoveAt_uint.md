# CMILObjectArray<RDFItem *>::RemoveAt(uint)

- ea: `0x180020c80`
- end: `0x180020cf0`
- name: `?RemoveAt@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJI@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017d40`
- `0x180020ae0`

## callees

- `0x1800171c4`
- `0x180020c80`
- `0x180032dcd`

## pseudocode

```c
__int64 __fastcall CMILObjectArray<RDFItem *>::RemoveAt(__int64 *a1, unsigned int a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbx

  v3 = a2;
  if ( a2 >= *((_DWORD *)a1 + 6) && g_doStackCaptures )
    DoStackCapture(-2147024809);
  if ( *((_DWORD *)a1 + 6) - (_DWORD)v3 != 1 )
  {
    v4 = *a1;
    memmove_0(
      (void *)(*a1 + 8 * v3),
      (const void *)(*a1 + 8LL * (unsigned int)(v3 + 1)),
      8LL * (unsigned int)(*((_DWORD *)a1 + 6) - v3 - 1));
    *(_QWORD *)(v4 + 8LL * (unsigned int)(*((_DWORD *)a1 + 6) - 1)) = 0;
  }
  --*((_DWORD *)a1 + 6);
  return 0;
}

```

## disassembly

```asm
0x180020c80  mov     [rsp+arg_0], rbx
0x180020c85  mov     [rsp+arg_8], rsi
0x180020c8a  push    rdi
0x180020c8b  sub     rsp, 20h
0x180020c8f  mov     rdi, rcx
0x180020c92  mov     esi, edx
0x180020c94  cmp     edx, [rcx+18h]
0x180020c97  jb      short loc_180020CAC
0x180020c99  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020ca0  jz      short loc_180020CAC
0x180020ca2  mov     ecx, 80070057h; int
0x180020ca7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020cac  mov     eax, [rdi+18h]
0x180020caf  sub     eax, esi
0x180020cb1  sub     eax, 1
0x180020cb4  jz      short loc_180020CDB
0x180020cb6  mov     rbx, [rdi]
0x180020cb9  mov     r8d, eax
0x180020cbc  lea     eax, [rsi+1]
0x180020cbf  shl     r8, 3; Size
0x180020cc3  lea     rdx, [rbx+rax*8]; Src
0x180020cc7  lea     rcx, [rbx+rsi*8]; void *
0x180020ccb  call    memmove_0
0x180020cd0  mov     ecx, [rdi+18h]
0x180020cd3  dec     ecx
0x180020cd5  xor     eax, eax
0x180020cd7  mov     [rbx+rcx*8], rax
0x180020cdb  dec     dword ptr [rdi+18h]
0x180020cde  mov     rbx, [rsp+28h+arg_0]
0x180020ce3  xor     eax, eax
0x180020ce5  mov     rsi, [rsp+28h+arg_8]
0x180020cea  add     rsp, 20h
0x180020cee  pop     rdi
0x180020cef  retn
```
