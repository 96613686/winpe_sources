# CFveHardwareEncryptionSettings::IsAlgorithmInList(ushort *,unsigned __int64,ushort const *,int *)

- ea: `0x180068ffc`
- end: `0x180069182`
- name: `?IsAlgorithmInList@CFveHardwareEncryptionSettings@@CAJPEAG_KPEBGPEAH@Z`
- size: `390`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068c80`

## callees

- `0x18000f760`
- `0x180030ab4`
- `0x180044324`
- `0x180068ffc`
- `0x180079fd4`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180069125`
- `ntdll!RtlCompareMemory` at `0x180069125`

## pseudocode

```c
__int64 __fastcall CFveHardwareEncryptionSettings::IsAlgorithmInList(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned __int16 *v6; // rdi
  int v7; // ebx
  unsigned __int16 *v8; // r14
  int v9; // r13d
  unsigned __int16 *v10; // rsi
  SIZE_T v11; // r15
  SIZE_T v12; // rbp
  int v13; // eax
  unsigned __int64 v15; // [rsp+70h] [rbp+8h] BYREF
  SIZE_T Length; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int64 v17; // [rsp+80h] [rbp+18h] BYREF
  int *v18; // [rsp+88h] [rbp+20h]

  v18 = a4;
  v17 = 0;
  Length = 0;
  v6 = a1;
  v15 = 0;
  v7 = 0;
  *a4 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a3 )
  {
    v7 = StringCchLengthW(a3, 0x100u, &v17);
    if ( v7 >= 0 )
    {
      v7 = ULongLongMult(a2, 2u, &v15);
      if ( v7 >= 0 )
      {
        v8 = (unsigned __int16 *)((char *)v6 + v15);
        if ( (unsigned __int16 *)((char *)v6 + v15) < v6 )
          return (unsigned int)-2147024362;
        v9 = 1;
        v10 = v6;
        if ( v8 != &v6[a2] )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v7 = 0;
        while ( 1 )
        {
          if ( v6 > v8 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( v10 > v8 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( *v10 == 59 || !*v10 || v10 == v8 )
          {
            if ( v6 > v10 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v7 = ULongLongSub((unsigned __int64)v10, (unsigned __int64)v6, &Length);
            if ( v7 < 0 )
              return (unsigned int)v7;
            v11 = Length;
            v12 = Length >> 1;
            if ( &v6[Length >> 1] != v10 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( v12 == v17 && RtlCompareMemory(v6, a3, v11) == v11 )
            {
              *v18 = 1;
              return (unsigned int)v7;
            }
            v6 = v10 + 1;
            v13 = 0;
            if ( *v10 == 59 )
              v13 = v9;
            v9 = v13;
          }
          if ( !v9 )
            return (unsigned int)v7;
          ++v10;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180068ffc  mov     rax, rsp
0x180068fff  mov     [rax+20h], r9
0x180069003  push    rbx
0x180069004  push    rbp
0x180069005  push    rsi
0x180069006  push    rdi
0x180069007  push    r12
0x180069009  push    r13
0x18006900b  push    r14
0x18006900d  push    r15
0x18006900f  sub     rsp, 28h
0x180069013  xor     r15d, r15d
0x180069016  mov     r12, r8
0x180069019  mov     [rax+18h], r15
0x18006901d  mov     rbp, rdx
0x180069020  mov     [rax+10h], r15
0x180069024  mov     rdi, rcx
0x180069027  mov     [rax+8], r15
0x18006902b  mov     ebx, r15d
0x18006902e  mov     [r9], r15d
0x180069031  test    rcx, rcx
0x180069034  jnz     short loc_18006903B
0x180069036  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pszAllowedAlgorithms != NULL")
0x18006903b  test    rbp, rbp
0x18006903e  jnz     short loc_180069045
0x180069040  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "cchAllowedAlgorithms != 0")
0x180069045  test    r12, r12
0x180069048  jz      loc_18006916E
0x18006904e  lea     r8, [rsp+68h+arg_10]; unsigned __int64 *
0x180069056  mov     edx, 100h; unsigned __int64
0x18006905b  mov     rcx, r12; unsigned __int16 *
0x18006905e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180069063  mov     ebx, eax
0x180069065  test    eax, eax
0x180069067  js      loc_18006916E
0x18006906d  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x180069072  mov     edx, 2; unsigned __int64
0x180069077  mov     rcx, rbp; unsigned __int64
0x18006907a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006907f  mov     ebx, eax
0x180069081  test    eax, eax
0x180069083  js      loc_18006916E
0x180069089  mov     r14, [rsp+68h+arg_0]
0x18006908e  add     r14, rdi
0x180069091  cmp     r14, rdi
0x180069094  jb      loc_180069169
0x18006909a  lea     rax, [rdi+rbp*2]
0x18006909e  mov     r13d, 1
0x1800690a4  mov     rsi, rdi
0x1800690a7  cmp     r14, rax
0x1800690aa  jz      short loc_1800690B1
0x1800690ac  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psEnd == pszAllowedAlgorithms + cchAllowedAlgorithms")
0x1800690b1  mov     ebx, r15d
0x1800690b4  cmp     rdi, r14
0x1800690b7  jbe     short loc_1800690BE
0x1800690b9  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart <= psEnd")
0x1800690be  cmp     rsi, r14
0x1800690c1  jbe     short loc_1800690C8
0x1800690c3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psCurrentPos <= psEnd")
0x1800690c8  cmp     word ptr [rsi], 3Bh ; ';'
0x1800690cc  jz      short loc_1800690D9
0x1800690ce  cmp     [rsi], r15w
0x1800690d2  jz      short loc_1800690D9
0x1800690d4  cmp     rsi, r14
0x1800690d7  jnz     short loc_18006914B
0x1800690d9  cmp     rdi, rsi
0x1800690dc  jbe     short loc_1800690E3
0x1800690de  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart <= psCurrentPos")
0x1800690e3  lea     r8, [rsp+68h+Length]; unsigned __int64 *
0x1800690e8  mov     rdx, rdi; unsigned __int64
0x1800690eb  mov     rcx, rsi; unsigned __int64
0x1800690ee  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800690f3  mov     ebx, eax
0x1800690f5  test    eax, eax
0x1800690f7  js      short loc_18006916E
0x1800690f9  mov     r15, [rsp+68h+Length]
0x1800690fe  mov     rbp, r15
0x180069101  shr     rbp, 1
0x180069104  lea     rax, [rdi+rbp*2]
0x180069108  cmp     rax, rsi
0x18006910b  jz      short loc_180069112
0x18006910d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart + cchToken == psCurrentPos")
0x180069112  cmp     rbp, [rsp+68h+arg_10]
0x18006911a  jnz     short loc_180069136
0x18006911c  mov     r8, r15; Length
0x18006911f  mov     rdx, r12; Source2
0x180069122  mov     rcx, rdi; Source1
0x180069125  call    cs:__imp_RtlCompareMemory
0x18006912c  nop     dword ptr [rax+rax+00h]
0x180069131  cmp     rax, r15
0x180069134  jz      short loc_180069159
0x180069136  xor     r15d, r15d
0x180069139  lea     rdi, [rsi+2]
0x18006913d  cmp     word ptr [rsi], 3Bh ; ';'
0x180069141  mov     eax, r15d
0x180069144  cmovz   eax, r13d
0x180069148  mov     r13d, eax
0x18006914b  test    r13d, r13d
0x18006914e  jz      short loc_18006916E
0x180069150  add     rsi, 2
0x180069154  jmp     loc_1800690B4
0x180069159  mov     rax, [rsp+68h+arg_18]
0x180069161  mov     dword ptr [rax], 1
0x180069167  jmp     short loc_18006916E
0x180069169  mov     ebx, 80070216h
0x18006916e  mov     eax, ebx
0x180069170  add     rsp, 28h
0x180069174  pop     r15
0x180069176  pop     r14
0x180069178  pop     r13
0x18006917a  pop     r12
0x18006917c  pop     rdi
0x18006917d  pop     rsi
0x18006917e  pop     rbp
0x18006917f  pop     rbx
0x180069180  retn
```
