# CLimitedMakeValidAccumulator::Reset(void)

- ea: `0x100427780`
- end: `0x100427872`
- name: `?Reset@CLimitedMakeValidAccumulator@@MEAAJXZ`
- size: `242`
- prototype: `__int64 __fastcall(CLimitedMakeValidAccumulator *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1004275b0`
- `0x100427780`
- `0x100427880`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004277e1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004277e1`

## string_xrefs

- `0x1004277cb`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLimitedMakeValidAccumulator::Reset(CLimitedMakeValidAccumulator *this)
{
  CLimitedGeodeticOutline *v2; // rcx
  CLimitedGeodeticOutline *v3; // rdi
  CLimitedGeodeticOutline *v4; // rax
  __int64 result; // rax
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v2 = (CLimitedGeodeticOutline *)*((_QWORD *)this + 6);
  if ( v2 )
    CLimitedGeodeticOutline::`scalar deleting destructor'(v2, 1u);
  v3 = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  if ( g_SOSHost )
    v4 = (CLimitedGeodeticOutline *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                                      g_SOSMemObj,
                                      1304,
                                      "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                                      26);
  else
    v4 = (CLimitedGeodeticOutline *)malloc(0x518u);
  v6 = (__int64)v4;
  if ( v4 )
    v3 = CLimitedGeodeticOutline::CLimitedGeodeticOutline(
           v4,
           *((double *)this + 9),
           (CLimitedMakeValidAccumulator *)((char *)this + 88),
           (CLimitedMakeValidAccumulator *)((char *)this + 24),
           *((double *)this + 10));
  *((_QWORD *)this + 6) = v3;
  if ( !v3 )
    return 2147942414LL;
  v6 = 0x300000002LL;
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*((_QWORD *)v3 + 54) + 8LL))(
             (__int64)v3 + 432,
             2,
             &v6);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    *((_QWORD *)this + 1) = *((_QWORD *)this + 6);
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x100427780  push    rdi
0x100427782  sub     rsp, 40h
0x100427786  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042778f  mov     [rsp+48h+arg_8], rbx
0x100427794  mov     rbx, rcx
0x100427797  mov     rcx, [rcx+30h]; this
0x10042779b  test    rcx, rcx
0x10042779e  jz      short loc_1004277AA
0x1004277a0  mov     edx, 1; unsigned int
0x1004277a5  call    ??_GCLimitedGeodeticOutline@@QEAAPEAXI@Z; CLimitedGeodeticOutline::`scalar deleting destructor'(uint)
0x1004277aa  xor     edi, edi
0x1004277ac  mov     [rbx+30h], rdi
0x1004277b0  mov     [rbx+8], rdi
0x1004277b4  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x1004277bb  jz      short loc_1004277DC
0x1004277bd  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004277c4  mov     rax, [rcx]
0x1004277c7  lea     r9d, [rdi+1Ah]
0x1004277cb  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004277d2  mov     edx, 518h
0x1004277d7  call    qword ptr [rax+78h]
0x1004277da  jmp     short loc_1004277E7
0x1004277dc  mov     ecx, 518h; Size
0x1004277e1  call    cs:__imp_malloc
0x1004277e7  mov     [rsp+48h+arg_0], rax
0x1004277ec  test    rax, rax
0x1004277ef  jz      short loc_100427814
0x1004277f1  lea     r9, [rbx+18h]; struct CGeometrySinkD *
0x1004277f5  lea     r8, [rbx+58h]; struct CPoint3D *
0x1004277f9  movsd   xmm0, qword ptr [rbx+50h]
0x1004277fe  movsd   [rsp+48h+var_28], xmm0; double
0x100427804  movsd   xmm1, qword ptr [rbx+48h]; double
0x100427809  mov     rcx, rax; this
0x10042780c  call    ??0CLimitedGeodeticOutline@@QEAA@NAEBVCPoint3D@@PEAVCGeometrySinkD@@N@Z; CLimitedGeodeticOutline::CLimitedGeodeticOutline(double,CPoint3D const &,CGeometrySinkD *,double)
0x100427811  mov     rdi, rax
0x100427814  mov     [rbx+30h], rdi
0x100427818  test    rdi, rdi
0x10042781b  jnz     short loc_10042782D
0x10042781d  mov     eax, 8007000Eh
0x100427822  mov     rbx, [rsp+48h+arg_8]
0x100427827  add     rsp, 40h
0x10042782b  pop     rdi
0x10042782c  retn
0x10042782d  mov     dword ptr [rsp+48h+arg_0], 2
0x100427835  mov     dword ptr [rsp+48h+arg_0+4], 3
0x10042783d  lea     rcx, [rdi+1B0h]
0x100427844  mov     rax, [rcx]
0x100427847  lea     r8, [rsp+48h+arg_0]
0x10042784c  mov     edx, 2
0x100427851  call    qword ptr [rax+8]
0x100427854  mov     ecx, eax
0x100427856  lfence
0x100427859  test    eax, eax
0x10042785b  js      short loc_100427867
0x10042785d  mov     rax, [rbx+30h]
0x100427861  mov     [rbx+8], rax
0x100427865  mov     eax, ecx
0x100427867  mov     rbx, [rsp+48h+arg_8]
0x10042786c  add     rsp, 40h
0x100427870  pop     rdi
0x100427871  retn
```
