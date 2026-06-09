# Spectre::Engine::Sampler::AttachDeviceSampler(std::shared_ptr<Spectre::Engine::DeviceSampler> const &)

- ea: `0x1800504f0`
- end: `0x180050602`
- name: `?AttachDeviceSampler@Sampler@Engine@Spectre@@QEAAXAEBV?$shared_ptr@VDeviceSampler@Engine@Spectre@@@std@@@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800686bc`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800504f0`
- `0x180050608`
- `0x1800681a8`

## string_xrefs

- `0x1800505c8`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\sampler.cpp`
- `0x1800505b6`: `Attaching a device sampler to an incompatible sampler`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Spectre::Engine::Sampler::AttachDeviceSampler(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  int v5; // eax
  int v6; // r8d
  _BYTE v7[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  v2 = *(_QWORD *)(a1 + 112);
  v3 = *(_QWORD *)(*(_QWORD *)a2 + 96LL);
  if ( *(_DWORD *)v2 != *(_DWORD *)v3
    || *(_DWORD *)(v2 + 4) != *(_DWORD *)(v3 + 4)
    || *(_DWORD *)(v2 + 8) != *(_DWORD *)(v3 + 8)
    || *(_DWORD *)(v2 + 12) != *(_DWORD *)(v3 + 12)
    || *(float *)(v2 + 16) != *(float *)(v3 + 16)
    || *(_DWORD *)(v2 + 20) != *(_DWORD *)(v3 + 20)
    || *(_DWORD *)(v2 + 24) != *(_DWORD *)(v3 + 24)
    || _mm_movemask_ps(_mm_cmpeq_ps(*(__m128 *)(v3 + 28), *(__m128 *)(v2 + 28))) != 15
    || *(float *)(v2 + 44) != *(float *)(v3 + 44)
    || *(float *)(v2 + 48) != *(float *)(v3 + 48) )
  {
    std::string::string(v8, "Attaching a device sampler to an incompatible sampler");
    v5 = std::string::string(
           v7,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\sampler.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v5, v6, (unsigned int)v8, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  return Spectre::Engine::Sampler::AttachDeviceSamplerInternal();
}

```

## disassembly

```asm
0x1800504f0  sub     rsp, 0C8h
0x1800504f7  mov     rax, cs:__security_cookie
0x1800504fe  xor     rax, rsp
0x180050501  mov     [rsp+0C8h+var_18], rax
0x180050509  mov     r8, [rcx+70h]
0x18005050d  mov     rax, [rdx]
0x180050510  mov     r9, [rax+60h]
0x180050514  mov     eax, [r9]
0x180050517  cmp     [r8], eax
0x18005051a  jnz     loc_1800505B6
0x180050520  mov     eax, [r9+4]
0x180050524  cmp     [r8+4], eax
0x180050528  jnz     loc_1800505B6
0x18005052e  mov     eax, [r9+8]
0x180050532  cmp     [r8+8], eax
0x180050536  jnz     short loc_1800505B6
0x180050538  mov     eax, [r9+0Ch]
0x18005053c  cmp     [r8+0Ch], eax
0x180050540  jnz     short loc_1800505B6
0x180050542  movss   xmm0, dword ptr [r8+10h]
0x180050548  ucomiss xmm0, dword ptr [r9+10h]
0x18005054d  jp      short loc_1800505B6
0x18005054f  jnz     short loc_1800505B6
0x180050551  mov     eax, [r9+14h]
0x180050555  cmp     [r8+14h], eax
0x180050559  jnz     short loc_1800505B6
0x18005055b  mov     eax, [r9+18h]
0x18005055f  cmp     [r8+18h], eax
0x180050563  jnz     short loc_1800505B6
0x180050565  movups  xmm1, xmmword ptr [r9+1Ch]
0x18005056a  movups  xmm0, xmmword ptr [r8+1Ch]
0x18005056f  cmpeqps xmm1, xmm0
0x180050573  movmskps eax, xmm1
0x180050576  cmp     eax, 0Fh
0x180050579  jnz     short loc_1800505B6
0x18005057b  movss   xmm0, dword ptr [r8+2Ch]
0x180050581  ucomiss xmm0, dword ptr [r9+2Ch]
0x180050586  jp      short loc_1800505B6
0x180050588  jnz     short loc_1800505B6
0x18005058a  movss   xmm0, dword ptr [r8+30h]
0x180050590  ucomiss xmm0, dword ptr [r9+30h]
0x180050595  jp      short loc_1800505B6
0x180050597  jnz     short loc_1800505B6
0x180050599  call    ?AttachDeviceSamplerInternal@Sampler@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VDeviceSampler@Engine@Spectre@@@std@@@Z; Spectre::Engine::Sampler::AttachDeviceSamplerInternal(std::shared_ptr<Spectre::Engine::DeviceSampler> const &)
0x18005059e  mov     rcx, [rsp+0C8h+var_18]
0x1800505a6  xor     rcx, rsp; StackCookie
0x1800505a9  call    __security_check_cookie
0x1800505ae  add     rsp, 0C8h
0x1800505b5  retn
0x1800505b6  lea     rdx, aAttachingADevi_0; "Attaching a device sampler to an incomp"...
0x1800505bd  lea     rcx, [rsp+0C8h+var_70]
0x1800505c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800505c7  nop
0x1800505c8  lea     rdx, aOnecoreuapWind_26; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800505cf  lea     rcx, [rsp+0C8h+var_90]
0x1800505d4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800505d9  mov     [rsp+0C8h+var_A8], 0
0x1800505de  lea     r9, [rsp+0C8h+var_70]
0x1800505e3  mov     rdx, rax
0x1800505e6  lea     rcx, [rsp+0C8h+pExceptionObject]
0x1800505eb  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800505f0  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800505f7  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800505fc  call    _CxxThrowException_0
```
