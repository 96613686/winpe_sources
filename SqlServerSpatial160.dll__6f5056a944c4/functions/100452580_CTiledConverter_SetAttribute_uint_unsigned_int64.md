# CTiledConverter::SetAttribute(uint,unsigned __int64)

- ea: `0x100452580`
- end: `0x10045266e`
- name: `?SetAttribute@CTiledConverter@@UEAAJI_K@Z`
- size: `238`
- prototype: `__int64 __fastcall(CTiledConverter *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100441de0`
- `0x100452580`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004525dd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004525dd`

## string_xrefs

- `0x1004525c7`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTiledConverter::SetAttribute(CTiledConverter *this, unsigned int a2, __int64 a3)
{
  CScanner *v6; // rax
  CScanner *v7; // rbx
  __int64 result; // rax

  if ( a2 != 4 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3);
  if ( g_SOSHost )
    v6 = (CScanner *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, __int64))(*g_SOSMemObj + 120LL))(
                       g_SOSMemObj,
                       528,
                       "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                       26,
                       -2);
  else
    v6 = (CScanner *)malloc(0x210u);
  v7 = v6;
  if ( v6 )
  {
    CScanner::CScanner(v6, 0, 0);
    *(_QWORD *)v7 = &COrientationChecker::COrientationScanner::`vftable';
    *((_DWORD *)v7 + 130) = 0;
  }
  *((_QWORD *)this + 34) = v7;
  if ( !v7 )
  {
    result = 2147942414LL;
    _mm_lfence();
    return result;
  }
  *((_DWORD *)this + 66) = 0;
  result = (*(__int64 (__fastcall **)(CScanner *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3);
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x100452580  push    rdi
0x100452582  sub     rsp, 30h
0x100452586  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10045258f  mov     [rsp+38h+arg_0], rbx
0x100452594  mov     [rsp+38h+arg_8], rbp
0x100452599  mov     [rsp+38h+arg_10], rsi
0x10045259e  mov     rbp, r8
0x1004525a1  mov     esi, edx
0x1004525a3  mov     rdi, rcx
0x1004525a6  cmp     edx, 4
0x1004525a9  jnz     loc_10045264A
0x1004525af  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x1004525b7  jz      short loc_1004525D8
0x1004525b9  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004525c0  mov     rax, [rcx]
0x1004525c3  lea     r9d, [rdx+16h]
0x1004525c7  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004525ce  mov     edx, 210h
0x1004525d3  call    qword ptr [rax+78h]
0x1004525d6  jmp     short loc_1004525E3
0x1004525d8  mov     ecx, 210h; Size
0x1004525dd  call    cs:__imp_malloc
0x1004525e3  mov     rbx, rax
0x1004525e6  mov     [rsp+38h+arg_18], rax
0x1004525eb  test    rbx, rbx
0x1004525ee  jz      short loc_100452611
0x1004525f0  xor     r8d, r8d; bool
0x1004525f3  xor     edx, edx; bool
0x1004525f5  mov     rcx, rax; this
0x1004525f8  call    ??0CScanner@@QEAA@_N0@Z; CScanner::CScanner(bool,bool)
0x1004525fd  lea     rax, ??_7COrientationScanner@COrientationChecker@@6B@; const COrientationChecker::COrientationScanner::`vftable'
0x100452604  mov     [rbx], rax
0x100452607  mov     dword ptr [rbx+208h], 0
0x100452611  mov     [rdi+110h], rbx
0x100452618  test    rbx, rbx
0x10045261b  jnz     short loc_100452627
0x10045261d  mov     eax, 8007000Eh
0x100452622  lfence
0x100452625  jmp     short loc_100452659
0x100452627  mov     dword ptr [rdi+108h], 0
0x100452631  mov     rax, [rbx]
0x100452634  xor     r8d, r8d
0x100452637  lea     edx, [r8+1]
0x10045263b  mov     rcx, rbx
0x10045263e  call    qword ptr [rax+18h]
0x100452641  test    eax, eax
0x100452643  jns     short loc_10045264A
0x100452645  lfence
0x100452648  jmp     short loc_100452659
0x10045264a  mov     rcx, [rdi+18h]
0x10045264e  mov     rax, [rcx]
0x100452651  mov     r8, rbp
0x100452654  mov     edx, esi
0x100452656  call    qword ptr [rax+8]
0x100452659  mov     rbx, [rsp+38h+arg_0]
0x10045265e  mov     rbp, [rsp+38h+arg_8]
0x100452663  mov     rsi, [rsp+38h+arg_10]
0x100452668  add     rsp, 30h
0x10045266c  pop     rdi
0x10045266d  retn
```
