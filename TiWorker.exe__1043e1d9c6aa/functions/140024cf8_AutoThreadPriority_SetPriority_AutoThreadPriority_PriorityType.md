# AutoThreadPriority::SetPriority(AutoThreadPriority::PriorityType)

- ea: `0x140024cf8`
- end: `0x140024e20`
- name: `?SetPriority@AutoThreadPriority@@QEAAXW4PriorityType@1@@Z`
- size: `296`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14001344c`
- `0x1400240f0`

## callees

- `0x140009118`
- `0x1400091b4`
- `0x14000e034`
- `0x1400246a0`
- `0x140024bf4`
- `0x140024cf8`

## pseudocode

```c
void __fastcall AutoThreadPriority::SetPriority(__int64 a1, int a2)
{
  char *v4; // rdx
  __m128i v5; // xmm2
  _BYTE v6[16]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v7[72]; // [rsp+40h] [rbp-48h] BYREF

  CritSecLocker::CritSecLocker((CritSecLocker *)v7, (struct AutoCritSec *)a1, 1);
  if ( a2 == *(_DWORD *)(a1 + 40) && (!*(_BYTE *)(a1 + 72) || a2) )
    goto LABEL_16;
  if ( *(_BYTE *)(a1 + 73) )
  {
    if ( a2 )
    {
LABEL_13:
      v5 = *(__m128i *)AutoThreadPriority::GetPlatformPriorityFromPriority((__int64)v6, a2);
      goto LABEL_14;
    }
  }
  else
  {
    if ( a2 )
    {
      switch ( a2 )
      {
        case 1:
          v4 = "Priority: Setting normal priority";
          break;
        case 2:
          v4 = "Priority: Setting user-away priority";
          break;
        case 3:
          v4 = "Priority: Setting user-present priority";
          break;
        case 4:
          v4 = "Priority: Setting normal priority with EcoQos";
          break;
        default:
          LogAdapter::TraceAtLevel<>(
            1,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Priority: Not setting unknown priority");
          goto LABEL_16;
      }
      LogAdapter::TraceAtLevel<>(1, (struct Windows::Rtl::IRtlFormattedOutputStream *)v4);
      goto LABEL_13;
    }
    LogAdapter::TraceAtLevel<>(
      1,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Priority: Restoring default priority");
  }
  v5 = *(__m128i *)(a1 + 56);
LABEL_14:
  AutoThreadPriority::SetPriority(
    a1,
    _mm_cvtsi128_si32(v5),
    _mm_cvtsi128_si32(_mm_srli_si128(v5, 4)),
    _mm_cvtsi128_si32(_mm_srli_si128(v5, 8)),
    _mm_cvtsi128_si32(_mm_srli_si128(v5, 12)));
  *(_DWORD *)(a1 + 40) = a2;
  if ( !a2 )
    *(_BYTE *)(a1 + 72) = 0;
LABEL_16:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v7);
}

```

## disassembly

```asm
0x140024cf8  push    rbx
0x140024cfa  push    rbp
0x140024cfb  push    rsi
0x140024cfc  push    rdi
0x140024cfd  sub     rsp, 68h
0x140024d01  mov     ebx, edx
0x140024d03  mov     rdi, rcx
0x140024d06  mov     rdx, rcx; struct AutoCritSec *
0x140024d09  mov     ebp, 1
0x140024d0e  mov     r8b, bpl; bool
0x140024d11  lea     rcx, [rsp+88h+var_48]; this
0x140024d16  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140024d1b  cmp     ebx, [rdi+28h]
0x140024d1e  jnz     short loc_140024D32
0x140024d20  cmp     byte ptr [rdi+48h], 0
0x140024d24  jz      loc_140024DD0
0x140024d2a  test    ebx, ebx
0x140024d2c  jnz     loc_140024DD0
0x140024d32  cmp     byte ptr [rdi+49h], 0
0x140024d36  jnz     loc_140024E0F
0x140024d3c  mov     edx, ebx
0x140024d3e  mov     ecx, ebp
0x140024d40  test    ebx, ebx
0x140024d42  jz      loc_140024E01
0x140024d48  sub     edx, ebp
0x140024d4a  jz      loc_140024DF5
0x140024d50  sub     edx, ebp
0x140024d52  jz      loc_140024DEC
0x140024d58  sub     edx, ebp
0x140024d5a  jz      loc_140024DE3
0x140024d60  cmp     edx, ebp
0x140024d62  jz      short loc_140024D72
0x140024d64  lea     rdx, aPriorityNotSet; "Priority: Not setting unknown priority"
0x140024d6b  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x140024d70  jmp     short loc_140024DD0
0x140024d72  lea     rdx, aPrioritySettin_1; "Priority: Setting normal priority with "...
0x140024d79  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x140024d7e  mov     edx, ebx
0x140024d80  lea     rcx, [rsp+88h+var_58]
0x140024d85  call    ?GetPlatformPriorityFromPriority@AutoThreadPriority@@SA?AUPlatformPriority@1@W4PriorityType@1@@Z; AutoThreadPriority::GetPlatformPriorityFromPriority(AutoThreadPriority::PriorityType)
0x140024d8a  movups  xmm2, xmmword ptr [rax]
0x140024d8d  movdqa  xmm0, xmm2
0x140024d91  movd    edx, xmm2
0x140024d95  psrldq  xmm0, 0Ch
0x140024d9a  movdqa  xmm1, xmm2
0x140024d9e  movd    eax, xmm0
0x140024da2  mov     rcx, rdi
0x140024da5  movdqa  xmm0, xmm2
0x140024da9  psrldq  xmm1, 4
0x140024dae  psrldq  xmm0, 8
0x140024db3  movd    r9d, xmm0
0x140024db8  movd    r8d, xmm1
0x140024dbd  mov     [rsp+88h+var_68], al
0x140024dc1  call    ?SetPriority@AutoThreadPriority@@AEAAXHW4_IO_PRIORITY_HINT@@K_N@Z; AutoThreadPriority::SetPriority(int,_IO_PRIORITY_HINT,ulong,bool)
0x140024dc6  mov     [rdi+28h], ebx
0x140024dc9  test    ebx, ebx
0x140024dcb  jnz     short loc_140024DD0
0x140024dcd  mov     [rdi+48h], bl
0x140024dd0  lea     rcx, [rsp+88h+var_48]; this
0x140024dd5  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x140024dda  add     rsp, 68h
0x140024dde  pop     rdi
0x140024ddf  pop     rsi
0x140024de0  pop     rbp
0x140024de1  pop     rbx
0x140024de2  retn
0x140024de3  lea     rdx, aPrioritySettin_0; "Priority: Setting user-present priority"
0x140024dea  jmp     short loc_140024D79
0x140024dec  lea     rdx, aPrioritySettin; "Priority: Setting user-away priority"
0x140024df3  jmp     short loc_140024D79
0x140024df5  lea     rdx, aPrioritySettin_2; "Priority: Setting normal priority"
0x140024dfc  jmp     loc_140024D79
0x140024e01  lea     rdx, aPriorityRestor; "Priority: Restoring default priority"
0x140024e08  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x140024e0d  jmp     short loc_140024E17
0x140024e0f  test    ebx, ebx
0x140024e11  jnz     loc_140024D7E
0x140024e17  movups  xmm2, xmmword ptr [rdi+38h]
0x140024e1b  jmp     loc_140024D8D
```
