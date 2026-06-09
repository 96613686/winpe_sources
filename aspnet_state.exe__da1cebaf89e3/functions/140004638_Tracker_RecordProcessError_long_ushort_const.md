# Tracker::RecordProcessError(long,ushort const *)

- ea: `0x140004638`
- end: `0x140004726`
- name: `?RecordProcessError@Tracker@@AEAAXJPEBG@Z`
- size: `238`
- prototype: `void __fastcall(Tracker *this, int, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x140003774`
- `0x140003a9c`
- `0x140003bb0`
- `0x140004108`
- `0x140004280`
- `0x140004410`
- `0x140004490`
- `0x1400044f0`
- `0x140004ba4`

## callees

- `0x140003f18`
- `0x140004638`
- `0x140004c14`
- `0x140004cd0`
- `0x140004f58`
- `0x140004fc8`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x140004676`
- `KERNEL32!lstrlenW` at `0x140004688`
- `KERNEL32!lstrlenW` at `0x140004676`
- `KERNEL32!lstrlenW` at `0x140004688`

## pseudocode

```c
void __fastcall Tracker::RecordProcessError(Tracker *this, int a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  int v7; // eax
  const WCHAR *v8; // rcx
  int v9; // edi
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax

  v3 = 0;
  if ( a2 && !(unsigned int)Tracker::IsExpectedError(this, a2) )
  {
    if ( !*((_DWORD *)this + 6) )
      *((_DWORD *)this + 6) = a2;
    v7 = lstrlenW(a3);
    v8 = (const WCHAR *)*((_QWORD *)this + 2);
    v9 = v7 + 1;
    if ( v8 )
      v9 += lstrlenW(v8) + 3;
    v10 = v9;
    v11 = (unsigned __int16 *)MemAlloc(saturated_mul(v9, 2u));
    v3 = v11;
    if ( v11
      && !(unsigned int)StringCchCopyW(v11, v10, a3)
      && (!*((_QWORD *)this + 2)
       || !(unsigned int)StringCchCatW(v3, v10, L"-->")
       && !(unsigned int)StringCchCatW(v3, v10, *((const unsigned __int16 **)this + 2))) )
    {
      MemFree(*((void **)this + 2));
      *((_QWORD *)this + 2) = v3;
      v3 = 0;
    }
  }
  MemFree(v3);
}

```

## disassembly

```asm
0x140004638  mov     [rsp+arg_0], rbx
0x14000463d  mov     [rsp+arg_8], rbp
0x140004642  mov     [rsp+arg_10], rsi
0x140004647  push    rdi
0x140004648  sub     rsp, 20h
0x14000464c  xor     edi, edi
0x14000464e  mov     rbp, r8
0x140004651  mov     esi, edx
0x140004653  mov     rbx, rcx
0x140004656  test    edx, edx
0x140004658  jz      loc_14000470A
0x14000465e  call    ?IsExpectedError@Tracker@@AEAAHJ@Z; Tracker::IsExpectedError(long)
0x140004663  test    eax, eax
0x140004665  jnz     loc_14000470A
0x14000466b  cmp     [rbx+18h], edi
0x14000466e  jnz     short loc_140004673
0x140004670  mov     [rbx+18h], esi
0x140004673  mov     rcx, rbp; lpString
0x140004676  call    cs:__imp_lstrlenW
0x14000467c  mov     rcx, [rbx+10h]; lpString
0x140004680  lea     edi, [rax+1]
0x140004683  test    rcx, rcx
0x140004686  jz      short loc_140004693
0x140004688  call    cs:__imp_lstrlenW
0x14000468e  add     eax, 3
0x140004691  add     edi, eax
0x140004693  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000469a  movsxd  rsi, edi
0x14000469d  mov     eax, 2
0x1400046a2  mul     rsi
0x1400046a5  cmovo   rax, rcx
0x1400046a9  mov     rcx, rax; unsigned __int64
0x1400046ac  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1400046b1  mov     rdi, rax
0x1400046b4  test    rax, rax
0x1400046b7  jz      short loc_14000470A
0x1400046b9  mov     r8, rbp; unsigned __int16 *
0x1400046bc  mov     rdx, rsi; unsigned __int64
0x1400046bf  mov     rcx, rax; unsigned __int16 *
0x1400046c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400046c7  test    eax, eax
0x1400046c9  jnz     short loc_14000470A
0x1400046cb  cmp     qword ptr [rbx+10h], 0
0x1400046d0  jz      short loc_1400046FB
0x1400046d2  lea     r8, asc_140007B00; "-->"
0x1400046d9  mov     rdx, rsi; unsigned __int64
0x1400046dc  mov     rcx, rdi; unsigned __int16 *
0x1400046df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400046e4  test    eax, eax
0x1400046e6  jnz     short loc_14000470A
0x1400046e8  mov     r8, [rbx+10h]; unsigned __int16 *
0x1400046ec  mov     rdx, rsi; unsigned __int64
0x1400046ef  mov     rcx, rdi; unsigned __int16 *
0x1400046f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400046f7  test    eax, eax
0x1400046f9  jnz     short loc_14000470A
0x1400046fb  mov     rcx, [rbx+10h]; lpMem
0x1400046ff  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x140004704  mov     [rbx+10h], rdi
0x140004708  xor     edi, edi
0x14000470a  mov     rcx, rdi; lpMem
0x14000470d  mov     rbx, [rsp+28h+arg_0]
0x140004712  mov     rbp, [rsp+28h+arg_8]
0x140004717  mov     rsi, [rsp+28h+arg_10]
0x14000471c  add     rsp, 20h
0x140004720  pop     rdi
0x140004721  jmp     ?MemFree@@YAXPEAX@Z; MemFree(void *)
```
