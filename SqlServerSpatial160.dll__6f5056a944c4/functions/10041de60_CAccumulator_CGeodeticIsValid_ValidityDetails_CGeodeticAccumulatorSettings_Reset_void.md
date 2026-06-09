# CAccumulator<CGeodeticIsValid,ValidityDetails,CGeodeticAccumulatorSettings>::Reset(void)

- ea: `0x10041de60`
- end: `0x10041dfd2`
- name: `?Reset@?$CAccumulator@VCGeodeticIsValid@@UValidityDetails@@UCGeodeticAccumulatorSettings@@@@IEAAJXZ`
- size: `370`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x10040bb10`
- `0x1004185a0`
- `0x100418a90`
- `0x10041ddc0`

## callees

- `0x10041de60`
- `0x10041e4f0`
- `0x100461a80`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10041decb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10041decb`

## string_xrefs

- `0x10041deb5`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAccumulator<CGeodeticIsValid,ValidityDetails,CGeodeticAccumulatorSettings>::Reset(_QWORD *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  char *v3; // rax
  char *v4; // rbx
  __int64 v6; // rcx
  __int64 v7; // xmm6_8

  v2 = (void (__fastcall ***)(_QWORD, __int64))a1[5];
  if ( v2 )
    (**v2)(v2, 1);
  a1[5] = 0;
  a1[4] = 0;
  if ( g_SOSHost )
    v3 = (char *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                   g_SOSMemObj,
                   5352,
                   "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                   26);
  else
    v3 = (char *)malloc(0x14E8u);
  v4 = v3;
  if ( v3 )
  {
    CIsValidChecker<CGeodeticLineStringChecker,CGeodeticPolygonsChecker>::CIsValidChecker<CGeodeticLineStringChecker,CGeodeticPolygonsChecker>(v3);
    *(_QWORD *)v4 = &CGeodeticIsValid::`vftable';
    *((_QWORD *)v4 + 659) = 0x3FF0000000000000LL;
    *((_DWORD *)v4 + 1320) = 0;
    *((_DWORD *)v4 + 1332) = 0;
    *(_QWORD *)(v4 + 5332) = -1;
    *((_DWORD *)v4 + 1335) = 0;
    v4[5344] = 0;
    v4[5348] = 0;
  }
  else
  {
    v4 = 0;
  }
  a1[5] = v4;
  if ( !v4 )
    return 2147942414LL;
  v6 = a1[8];
  v7 = a1[6];
  *((_QWORD *)v4 + 361) = a1[7];
  *((_QWORD *)v4 + 92) = v6;
  *((_QWORD *)v4 + 113) = v7;
  if ( (int)CGeodeticScannerConstruction::Set(
              *((CGeodeticScannerConstruction **)v4 + 360),
              *((const struct COriginalPoints **)v4 + 361),
              *((struct CGeometrySinkD **)v4 + 376),
              1.0,
              0) >= 0 )
    *((_QWORD *)v4 + 9) = v4 + 2864;
  *((_QWORD *)v4 + 470) = v7;
  *((_QWORD *)v4 + 656) = v4 + 3032;
  *((_QWORD *)v4 + 659) = v7;
  a1[4] = a1[5];
  return 0;
}

```

## disassembly

```asm
0x10041de60  push    rdi
0x10041de62  sub     rsp, 50h
0x10041de66  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x10041de6f  mov     [rsp+58h+arg_8], rbx
0x10041de74  mov     [rsp+58h+arg_10], rsi
0x10041de79  movaps  [rsp+58h+var_18], xmm6
0x10041de7e  mov     rdi, rcx
0x10041de81  mov     rcx, [rcx+28h]
0x10041de85  test    rcx, rcx
0x10041de88  jz      short loc_10041DE94
0x10041de8a  mov     rax, [rcx]
0x10041de8d  mov     edx, 1
0x10041de92  call    qword ptr [rax]
0x10041de94  xor     esi, esi
0x10041de96  mov     [rdi+28h], rsi
0x10041de9a  mov     [rdi+20h], rsi
0x10041de9e  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rsi; SOS_AutoHost g_SOSHost
0x10041dea5  jz      short loc_10041DEC6
0x10041dea7  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10041deae  mov     rax, [rcx]
0x10041deb1  lea     r9d, [rsi+1Ah]
0x10041deb5  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10041debc  mov     edx, 14E8h
0x10041dec1  call    qword ptr [rax+78h]
0x10041dec4  jmp     short loc_10041DED1
0x10041dec6  mov     ecx, 14E8h; Size
0x10041decb  call    cs:__imp_malloc
0x10041ded1  mov     rbx, rax
0x10041ded4  mov     [rsp+58h+arg_0], rax
0x10041ded9  test    rax, rax
0x10041dedc  jz      short loc_10041DF2F
0x10041dede  mov     rcx, rax
0x10041dee1  call    ??0?$CIsValidChecker@VCGeodeticLineStringChecker@@VCGeodeticPolygonsChecker@@@@QEAA@XZ; CIsValidChecker<CGeodeticLineStringChecker,CGeodeticPolygonsChecker>::CIsValidChecker<CGeodeticLineStringChecker,CGeodeticPolygonsChecker>(void)
0x10041dee6  nop
0x10041dee7  lea     rax, ??_7CGeodeticIsValid@@6B@; const CGeodeticIsValid::`vftable'
0x10041deee  mov     [rbx], rax
0x10041def1  mov     rax, 3FF0000000000000h
0x10041defb  mov     [rbx+1498h], rax
0x10041df02  mov     [rbx+14A0h], esi
0x10041df08  mov     [rbx+14D0h], esi
0x10041df0e  mov     qword ptr [rbx+14D4h], 0FFFFFFFFFFFFFFFFh
0x10041df19  mov     [rbx+14DCh], esi
0x10041df1f  mov     byte ptr [rbx+14E0h], 0
0x10041df26  mov     byte ptr [rbx+14E4h], 0
0x10041df2d  jmp     short loc_10041DF32
0x10041df2f  mov     rbx, rsi
0x10041df32  mov     [rdi+28h], rbx
0x10041df36  test    rbx, rbx
0x10041df39  jnz     short loc_10041DF42
0x10041df3b  mov     eax, 8007000Eh
0x10041df40  jmp     short loc_10041DFBD
0x10041df42  mov     rcx, [rdi+40h]
0x10041df46  movsd   xmm6, qword ptr [rdi+30h]
0x10041df4b  mov     rax, [rdi+38h]
0x10041df4f  mov     [rbx+0B48h], rax
0x10041df56  mov     [rbx+2E0h], rcx
0x10041df5d  movsd   qword ptr [rbx+388h], xmm6
0x10041df65  lea     rsi, [rbx+0B30h]
0x10041df6c  mov     [rsp+58h+var_38], 0; bool
0x10041df71  movsd   xmm3, cs:__real@3ff0000000000000; double
0x10041df79  mov     r8, [rsi+90h]; struct CGeometrySinkD *
0x10041df80  mov     rdx, [rsi+18h]; struct COriginalPoints *
0x10041df84  mov     rcx, [rsi+10h]; this
0x10041df88  call    ?Set@CGeodeticScannerConstruction@@QEAAJPEBVCOriginalPoints@@PEAVCGeometrySinkD@@N_N@Z; CGeodeticScannerConstruction::Set(COriginalPoints const *,CGeometrySinkD *,double,bool)
0x10041df8d  test    eax, eax
0x10041df8f  js      short loc_10041DF95
0x10041df91  mov     [rbx+48h], rsi
0x10041df95  movsd   qword ptr [rbx+0EB0h], xmm6
0x10041df9d  lea     rax, [rbx+0BD8h]
0x10041dfa4  mov     [rbx+1480h], rax
0x10041dfab  movsd   qword ptr [rbx+1498h], xmm6
0x10041dfb3  mov     rax, [rdi+28h]
0x10041dfb7  mov     [rdi+20h], rax
0x10041dfbb  xor     eax, eax
0x10041dfbd  mov     rbx, [rsp+58h+arg_8]
0x10041dfc2  mov     rsi, [rsp+58h+arg_10]
0x10041dfc7  movaps  xmm6, [rsp+58h+var_18]
0x10041dfcc  add     rsp, 50h
0x10041dfd0  pop     rdi
0x10041dfd1  retn
```
