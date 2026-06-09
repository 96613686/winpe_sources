# Spectre::Engine::Engine::UpdateStatistics(void)

- ea: `0x1800364a8`
- end: `0x18003657e`
- name: `?UpdateStatistics@Engine@1Spectre@@IEAAXXZ`
- size: `214`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180032720`

## callees

- `0x18001ff14`
- `0x1800294a4`
- `0x1800364a8`
- `0x18003cac0`

## string_xrefs

- `0x1800364cf`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800364ef`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800364c3`: `UpdateStatistics`

## pseudocode

```c
void __fastcall Spectre::Engine::Engine::UpdateStatistics(Spectre::Utils::PerformanceLogger **this)
{
  Spectre::Utils::PerformanceLogger *v2; // rcx
  __int64 *v3; // rdx
  char *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // [rsp+28h] [rbp-10h]

  Spectre::Utils::PerformanceLogger::AddMark(
    this[58],
    0,
    "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1661,
    "UpdateStatistics",
    "FrameTick");
  v8 = (char *)this[118];
  v2 = this[58];
  this[118] = (Spectre::Utils::PerformanceLogger *)(v8 + 1);
  Spectre::Utils::PerformanceLogger::AddMeasurement<unsigned __int64>(
    (_DWORD)v2,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1662,
    (unsigned int)"UpdateStatistics",
    (__int64)"FrameTick_FrameNumber",
    (__int64)v8);
  v3 = qword_180236D20;
  do
  {
    v4 = (char *)(v3 + 20);
    while ( v3 != (__int64 *)v4 )
    {
      v5 = std::_Atomic_storage<unsigned __int64,8>::load(v3);
      *(_QWORD *)(v6 + 16) += v5;
      *(_QWORD *)(v6 + 8) = v5;
      v7 = *(_QWORD *)(v6 + 24);
      if ( v7 < v5 )
        v7 = v5;
      *(_QWORD *)(v6 + 24) = v7;
      _InterlockedExchange64((volatile __int64 *)v6, 0);
      v3 = (__int64 *)(v6 + 32);
    }
    v3 = (__int64 *)v4;
  }
  while ( v4 != &byte_180237680 );
}

```

## disassembly

```asm
0x1800364a8  mov     [rsp+arg_0], rbx
0x1800364ad  push    rdi
0x1800364ae  sub     rsp, 30h
0x1800364b2  lea     rax, aFrametick; "FrameTick"
0x1800364b9  mov     rbx, rcx
0x1800364bc  mov     rcx, [rcx+1D0h]; this
0x1800364c3  lea     rdi, aUpdatestatisti; "UpdateStatistics"
0x1800364ca  mov     [rsp+38h+var_10], rax; char *
0x1800364cf  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800364d6  mov     r9d, 67Dh; int
0x1800364dc  mov     [rsp+38h+var_18], rdi; char *
0x1800364e1  xor     edx, edx; int
0x1800364e3  call    ?AddMark@PerformanceLogger@Utils@Spectre@@QEBAXHPEBDH00@Z; Spectre::Utils::PerformanceLogger::AddMark(int,char const *,int,char const *,char const *)
0x1800364e8  mov     rcx, [rbx+3B0h]
0x1800364ef  lea     rdx, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800364f6  mov     [rsp+38h+var_10], rcx
0x1800364fb  mov     r9, rdi
0x1800364fe  mov     r8d, 67Eh
0x180036504  lea     rax, [rcx+1]
0x180036508  mov     rcx, [rbx+1D0h]
0x18003650f  mov     [rbx+3B0h], rax
0x180036516  lea     rax, aFrametickFrame; "FrameTick_FrameNumber"
0x18003651d  mov     [rsp+38h+var_18], rax
0x180036522  call    ??$AddMeasurement@_K@PerformanceLogger@Utils@Spectre@@QEBAXPEBDH00_K@Z; Spectre::Utils::PerformanceLogger::AddMeasurement<unsigned __int64>(char const *,int,char const *,char const *,unsigned __int64)
0x180036527  lea     rdx, qword_180236D20
0x18003652e  lea     r8, [rdx+0A0h]
0x180036535  jmp     short loc_18003655F
0x180036537  mov     rcx, rdx
0x18003653a  call    ?load@?$_Atomic_storage@_K$07@std@@QEBA_KW4memory_order@2@@Z; std::_Atomic_storage<unsigned __int64,8>::load(std::memory_order)
0x18003653f  add     [rdx+10h], rax
0x180036543  mov     [rdx+8], rax
0x180036547  mov     rcx, [rdx+18h]
0x18003654b  cmp     rcx, rax
0x18003654e  cmovl   rcx, rax
0x180036552  xor     eax, eax
0x180036554  mov     [rdx+18h], rcx
0x180036558  xchg    rax, [rdx]
0x18003655b  add     rdx, 20h ; ' '
0x18003655f  cmp     rdx, r8
0x180036562  jnz     short loc_180036537
0x180036564  lea     rax, byte_180237680
0x18003656b  mov     rdx, r8
0x18003656e  cmp     r8, rax
0x180036571  jnz     short loc_18003652E
0x180036573  mov     rbx, [rsp+38h+arg_0]
0x180036578  add     rsp, 30h
0x18003657c  pop     rdi
0x18003657d  retn
```
