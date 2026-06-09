# CFullGlobeMakeValidAccumulator::Reset(void)

- ea: `0x100427360`
- end: `0x10042744d`
- name: `?Reset@CFullGlobeMakeValidAccumulator@@MEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(CFullGlobeMakeValidAccumulator *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x10040aa40`
- `0x100427360`
- `0x100461a80`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004273c1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004273c1`

## string_xrefs

- `0x1004273ab`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFullGlobeMakeValidAccumulator::Reset(CFullGlobeMakeValidAccumulator *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  CGeodeticOutline *v3; // rdi
  CGeodeticOutline *v4; // rax
  __int64 result; // rax

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 6);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  if ( g_SOSHost )
    v4 = (CGeodeticOutline *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                               g_SOSMemObj,
                               2688,
                               "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                               26);
  else
    v4 = (CGeodeticOutline *)malloc(0xA80u);
  if ( v4 )
    v3 = CGeodeticOutline::CGeodeticOutline(v4, *((double *)this + 9));
  *((_QWORD *)this + 6) = v3;
  if ( !v3 )
    return 2147942414LL;
  *(_BYTE *)(*((_QWORD *)v3 + 81) + 281LL) = 1;
  *(_BYTE *)(*((_QWORD *)v3 + 82) + 281LL) = 1;
  result = CGeodeticScannerConstruction::Set(
             *((CGeodeticScannerConstruction **)this + 6),
             0,
             (CFullGlobeMakeValidAccumulator *)((char *)this + 24),
             *((double *)this + 10),
             1);
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
0x100427360  push    rdi
0x100427362  sub     rsp, 40h
0x100427366  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042736f  mov     [rsp+48h+arg_8], rbx
0x100427374  mov     rbx, rcx
0x100427377  mov     rcx, [rcx+30h]
0x10042737b  test    rcx, rcx
0x10042737e  jz      short loc_10042738A
0x100427380  mov     rax, [rcx]
0x100427383  mov     edx, 1
0x100427388  call    qword ptr [rax]
0x10042738a  xor     edi, edi
0x10042738c  mov     [rbx+30h], rdi
0x100427390  mov     [rbx+8], rdi
0x100427394  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x10042739b  jz      short loc_1004273BC
0x10042739d  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004273a4  mov     rax, [rcx]
0x1004273a7  lea     r9d, [rdi+1Ah]
0x1004273ab  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004273b2  mov     edx, 0A80h
0x1004273b7  call    qword ptr [rax+78h]
0x1004273ba  jmp     short loc_1004273C7
0x1004273bc  mov     ecx, 0A80h; Size
0x1004273c1  call    cs:__imp_malloc
0x1004273c7  mov     [rsp+48h+arg_0], rax
0x1004273cc  test    rax, rax
0x1004273cf  jz      short loc_1004273E1
0x1004273d1  movsd   xmm1, qword ptr [rbx+48h]; double
0x1004273d6  mov     rcx, rax; this
0x1004273d9  call    ??0CGeodeticOutline@@QEAA@N@Z; CGeodeticOutline::CGeodeticOutline(double)
0x1004273de  mov     rdi, rax
0x1004273e1  mov     [rbx+30h], rdi
0x1004273e5  test    rdi, rdi
0x1004273e8  jnz     short loc_1004273FA
0x1004273ea  mov     eax, 8007000Eh
0x1004273ef  mov     rbx, [rsp+48h+arg_8]
0x1004273f4  add     rsp, 40h
0x1004273f8  pop     rdi
0x1004273f9  retn
0x1004273fa  mov     rax, [rdi+288h]
0x100427401  mov     byte ptr [rax+119h], 1
0x100427408  mov     rax, [rdi+290h]
0x10042740f  mov     byte ptr [rax+119h], 1
0x100427416  lea     r8, [rbx+18h]; struct CGeometrySinkD *
0x10042741a  mov     [rsp+48h+var_28], 1; bool
0x10042741f  movsd   xmm3, qword ptr [rbx+50h]; double
0x100427424  xor     edx, edx; struct COriginalPoints *
0x100427426  mov     rcx, [rbx+30h]; this
0x10042742a  call    ?Set@CGeodeticScannerConstruction@@QEAAJPEBVCOriginalPoints@@PEAVCGeometrySinkD@@N_N@Z; CGeodeticScannerConstruction::Set(COriginalPoints const *,CGeometrySinkD *,double,bool)
0x10042742f  mov     ecx, eax
0x100427431  lfence
0x100427434  test    eax, eax
0x100427436  js      short loc_100427442
0x100427438  mov     rax, [rbx+30h]
0x10042743c  mov     [rbx+8], rax
0x100427440  mov     eax, ecx
0x100427442  mov     rbx, [rsp+48h+arg_8]
0x100427447  add     rsp, 40h
0x10042744b  pop     rdi
0x10042744c  retn
```
