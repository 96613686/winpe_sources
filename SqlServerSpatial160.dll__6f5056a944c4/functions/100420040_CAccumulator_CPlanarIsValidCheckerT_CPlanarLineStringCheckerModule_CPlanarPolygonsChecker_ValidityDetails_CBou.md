# CAccumulator<CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>,ValidityDetails,CBoundsSettings<CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>>>::Reset(void)

- ea: `0x100420040`
- end: `0x100420192`
- name: `?Reset@?$CAccumulator@V?$CPlanarIsValidCheckerT@VCPlanarLineStringCheckerModule@@VCPlanarPolygonsChecker@@@@UValidityDetails@@U?$CBoundsSettings@V?$CPlanarIsValidCheckerT@VCPlanarLineStringCheckerModule@@VCPlanarPolygonsChecker@@@@@@@@IEAAJXZ`
- size: `338`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x100415880`
- `0x10041d500`

## callees

- `0x100420040`
- `0x100420f30`
- `0x100432b80`
- `0x10046985e`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004200a6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004200a6`

## string_xrefs

- `0x100420090`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccumulator<CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>,ValidityDetails,CBoundsSettings<CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>>>::Reset(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  double *v3; // rax
  double *v4; // rbx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 40);
  if ( v2 )
    (**v2)(v2, 1);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( g_SOSHost )
    v3 = (double *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, __int64))(*g_SOSMemObj + 120LL))(
                     g_SOSMemObj,
                     2032,
                     "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                     26,
                     -2);
  else
    v3 = (double *)malloc(0x7F0u);
  v4 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x7F0u);
    CIsValidChecker<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>::CIsValidChecker<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>(v4);
    *(_QWORD *)v4 = &CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>::`vftable';
  }
  else
  {
    v4 = 0;
  }
  *(_QWORD *)(a1 + 40) = v4;
  if ( !v4 )
    return 2147942414LL;
  if ( (int)CWorkspaceTransform::SetWithScaleFactor(v4 + 23, a1 + 48) >= 0 )
  {
    v4[48] = fmin(v4[33], v4[34]);
    _mm_lfence();
    if ( (int)CWorkspaceTransform::SetWithScaleFactor(v4 + 140, a1 + 48) >= 0 )
    {
      v4[165] = fmin(v4[150], v4[151]);
      *((_QWORD *)v4 + 251) = v4 + 163;
    }
  }
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 40);
  return 0;
}

```

## disassembly

```asm
0x100420040  push    rdi
0x100420042  sub     rsp, 30h
0x100420046  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10042004f  mov     [rsp+38h+arg_8], rbx
0x100420054  mov     [rsp+38h+arg_10], rsi
0x100420059  mov     rdi, rcx
0x10042005c  mov     rcx, [rcx+28h]
0x100420060  test    rcx, rcx
0x100420063  jz      short loc_10042006F
0x100420065  mov     rax, [rcx]
0x100420068  mov     edx, 1
0x10042006d  call    qword ptr [rax]
0x10042006f  xor     esi, esi
0x100420071  mov     [rdi+28h], rsi
0x100420075  mov     [rdi+20h], rsi
0x100420079  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rsi; SOS_AutoHost g_SOSHost
0x100420080  jz      short loc_1004200A1
0x100420082  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100420089  mov     rax, [rcx]
0x10042008c  lea     r9d, [rsi+1Ah]
0x100420090  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100420097  mov     edx, 7F0h
0x10042009c  call    qword ptr [rax+78h]
0x10042009f  jmp     short loc_1004200AC
0x1004200a1  mov     ecx, 7F0h; Size
0x1004200a6  call    cs:__imp_malloc
0x1004200ac  mov     rbx, rax
0x1004200af  mov     [rsp+38h+arg_0], rax
0x1004200b4  test    rax, rax
0x1004200b7  jz      short loc_1004200DE
0x1004200b9  xor     edx, edx; Val
0x1004200bb  mov     r8d, 7F0h; Size
0x1004200c1  mov     rcx, rax; void *
0x1004200c4  call    memset_0
0x1004200c9  mov     rcx, rbx
0x1004200cc  call    ??0?$CIsValidChecker@VCPlanarLineStringCheckerModule@@VCPlanarPolygonsChecker@@@@QEAA@XZ; CIsValidChecker<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>::CIsValidChecker<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>(void)
0x1004200d1  nop
0x1004200d2  lea     rax, ??_7?$CPlanarIsValidCheckerT@VCPlanarLineStringCheckerModule@@VCPlanarPolygonsChecker@@@@6B@; const CPlanarIsValidCheckerT<CPlanarLineStringCheckerModule,CPlanarPolygonsChecker>::`vftable'
0x1004200d9  mov     [rbx], rax
0x1004200dc  jmp     short loc_1004200E1
0x1004200de  mov     rbx, rsi
0x1004200e1  mov     [rdi+28h], rbx
0x1004200e5  test    rbx, rbx
0x1004200e8  jnz     short loc_1004200FF
0x1004200ea  mov     eax, 8007000Eh
0x1004200ef  mov     rbx, [rsp+38h+arg_8]
0x1004200f4  mov     rsi, [rsp+38h+arg_10]
0x1004200f9  add     rsp, 30h
0x1004200fd  pop     rdi
0x1004200fe  retn
0x1004200ff  lea     rcx, [rbx+0B8h]
0x100420106  movsd   xmm2, cs:__real@3ff0000000000000
0x10042010e  lea     rdx, [rdi+30h]
0x100420112  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x100420117  test    eax, eax
0x100420119  js      short loc_100420178
0x10042011b  movsd   xmm0, qword ptr [rbx+108h]
0x100420123  minsd   xmm0, qword ptr [rbx+110h]
0x10042012b  movsd   qword ptr [rbx+180h], xmm0
0x100420133  lfence
0x100420136  lea     rcx, [rbx+460h]
0x10042013d  movsd   xmm2, cs:__real@3ff0000000000000
0x100420145  lea     rdx, [rdi+30h]
0x100420149  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x10042014e  test    eax, eax
0x100420150  js      short loc_100420178
0x100420152  movsd   xmm0, qword ptr [rbx+4B0h]
0x10042015a  minsd   xmm0, qword ptr [rbx+4B8h]
0x100420162  movsd   qword ptr [rbx+528h], xmm0
0x10042016a  lea     rax, [rbx+518h]
0x100420171  mov     [rbx+7D8h], rax
0x100420178  mov     rax, [rdi+28h]
0x10042017c  mov     [rdi+20h], rax
0x100420180  xor     eax, eax
0x100420182  mov     rbx, [rsp+38h+arg_8]
0x100420187  mov     rsi, [rsp+38h+arg_10]
0x10042018c  add     rsp, 30h
0x100420190  pop     rdi
0x100420191  retn
```
