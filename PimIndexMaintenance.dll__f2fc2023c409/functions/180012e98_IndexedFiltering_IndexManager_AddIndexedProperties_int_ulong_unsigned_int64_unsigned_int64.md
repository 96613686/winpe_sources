# IndexedFiltering::IndexManager::AddIndexedProperties(int,ulong *,unsigned __int64,unsigned __int64 *)

- ea: `0x180012e98`
- end: `0x180012f5f`
- name: `?AddIndexedProperties@IndexManager@IndexedFiltering@@AEAAXHPEAK_KPEA_K@Z`
- size: `199`
- prototype: `void __fastcall(IndexedFiltering::IndexManager *__hidden this, int, unsigned int *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180013768`

## callees

- `0x1800086a0`
- `0x180012e98`

## string_xrefs

- `0x180012ecd`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180012f30`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
void __fastcall IndexedFiltering::IndexManager::AddIndexedProperties(
        IndexedFiltering::IndexManager *this,
        int a2,
        unsigned int *a3,
        unsigned __int64 a4,
        unsigned __int64 *a5)
{
  __int64 v9; // r15
  unsigned __int64 *v10; // rbx
  unsigned __int64 i; // rdi
  unsigned __int64 v12; // r8
  __int64 j; // rcx

  if ( !a3 || !a4 || !a5 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      844);
  v9 = *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 208);
  v10 = (unsigned __int64 *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 216);
  for ( i = 0; i < a4; ++i )
  {
    v12 = *a5;
    for ( j = 0; (unsigned int)j < v12; j = (unsigned int)(j + 1) )
    {
      if ( *(_DWORD *)(v9 + 4 * j) == a3[i] )
      {
        --*v10;
        goto LABEL_14;
      }
    }
    if ( v12 >= *v10 )
      Log_AssertionEvent(
        j,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
        870);
    *(_DWORD *)(v9 + 4 * (*a5)++) = a3[i];
LABEL_14:
    ;
  }
}

```

## disassembly

```asm
0x180012e98  push    rbx
0x180012e9a  push    rbp
0x180012e9b  push    rsi
0x180012e9c  push    rdi
0x180012e9d  push    r14
0x180012e9f  push    r15
0x180012ea1  sub     rsp, 28h
0x180012ea5  mov     rsi, [rsp+58h+arg_20]
0x180012ead  mov     rbp, r9
0x180012eb0  mov     r14, r8
0x180012eb3  mov     ebx, edx
0x180012eb5  mov     rdi, rcx
0x180012eb8  test    r8, r8
0x180012ebb  jz      short loc_180012EC7
0x180012ebd  test    r9, r9
0x180012ec0  jz      short loc_180012EC7
0x180012ec2  test    rsi, rsi
0x180012ec5  jnz     short loc_180012ED9
0x180012ec7  mov     r8d, 34Ch
0x180012ecd  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012ed4  call    Log_AssertionEvent
0x180012ed9  mov     eax, ebx
0x180012edb  neg     eax
0x180012edd  sbb     rcx, rcx
0x180012ee0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180012ee4  neg     ebx
0x180012ee6  sbb     rbx, rbx
0x180012ee9  mov     r15, [rcx+rdi+0D0h]
0x180012ef1  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180012ef5  add     rdi, 0D8h
0x180012efc  add     rbx, rdi
0x180012eff  xor     edi, edi
0x180012f01  test    rbp, rbp
0x180012f04  jz      short loc_180012F52
0x180012f06  mov     r8, [rsi]
0x180012f09  xor     ecx, ecx
0x180012f0b  mov     edx, ecx
0x180012f0d  cmp     rdx, r8
0x180012f10  jnb     short loc_180012F25
0x180012f12  mov     eax, [r14+rdi*4]
0x180012f16  cmp     [r15+rcx*4], eax
0x180012f1a  jz      short loc_180012F20
0x180012f1c  inc     ecx
0x180012f1e  jmp     short loc_180012F0B
0x180012f20  dec     qword ptr [rbx]
0x180012f23  jmp     short loc_180012F4A
0x180012f25  cmp     r8, [rbx]
0x180012f28  jb      short loc_180012F3C
0x180012f2a  mov     r8d, 366h
0x180012f30  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012f37  call    Log_AssertionEvent
0x180012f3c  mov     rcx, [rsi]
0x180012f3f  mov     eax, [r14+rdi*4]
0x180012f43  mov     [r15+rcx*4], eax
0x180012f47  inc     qword ptr [rsi]
0x180012f4a  inc     rdi
0x180012f4d  cmp     rdi, rbp
0x180012f50  jb      short loc_180012F06
0x180012f52  add     rsp, 28h
0x180012f56  pop     r15
0x180012f58  pop     r14
0x180012f5a  pop     rdi
0x180012f5b  pop     rsi
0x180012f5c  pop     rbp
0x180012f5d  pop     rbx
0x180012f5e  retn
```
