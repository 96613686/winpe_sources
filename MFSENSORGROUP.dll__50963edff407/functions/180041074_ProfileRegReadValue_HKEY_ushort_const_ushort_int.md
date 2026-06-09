# ProfileRegReadValue(HKEY__ *,ushort const *,ushort * *,int *)

- ea: `0x180041074`
- end: `0x180041250`
- name: `?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAPEAGPEAH@Z`
- size: `476`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180068590`
- `0x18006abc0`

## callees

- `0x180005fa0`
- `0x180041074`
- `0x180044b1c`
- `0x180044b28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800410fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004119f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800410fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004119f`
- `MFPlat!MFTraceError` at `0x1800411d8`
- `MFPlat!MFTraceError` at `0x18004123b`
- `MFPlat!MFTraceError` at `0x1800411d8`
- `MFPlat!MFTraceError` at `0x18004123b`

## string_xrefs

- `0x1800411be`: `ProfileRegReadValue`
- `0x18004122d`: `ProfileRegReadValue`

## pseudocode

```c
__int64 __fastcall ProfileRegReadValue(HKEY hkey, LPCWSTR lpValue, unsigned __int16 **a3, DWORD *a4)
{
  __int64 v8; // rdx
  LSTATUS ValueW; // eax
  unsigned int v10; // ebx
  void *pvData; // rax
  void *v12; // rdi
  LSTATUS v13; // eax
  DWORD v14; // eax
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF

  pcbData = 0;
  if ( (unsigned __int64)hkey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = 762;
    goto LABEL_20;
  }
  if ( a3 && a4 )
  {
    if ( !lpValue )
    {
      v8 = 764;
LABEL_20:
      v10 = -2147024809;
      MFTraceError(
        "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
        v8,
        "ProfileRegReadValue",
        0,
        -2147024809,
        1);
      return v10;
    }
    *a3 = 0;
    *a4 = 0;
    ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData);
    v10 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
      MFTraceError("avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp", 774, "ProfileRegReadValue", 0, v10, 1);
    }
    else
    {
      pvData = operator new[](pcbData);
      v12 = pvData;
      if ( pvData )
      {
        v13 = RegGetValueW(hkey, 0, lpValue, 2u, 0, pvData, &pcbData);
        v10 = v13;
        if ( v13 )
        {
          if ( v13 > 0 )
            v10 = (unsigned __int16)v13 | 0x80070000;
          MFTraceError(
            "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
            784,
            "ProfileRegReadValue",
            0,
            v10,
            1);
          operator delete(v12);
        }
        else
        {
          v10 = 0;
          v14 = pcbData >> 1;
          *a3 = (unsigned __int16 *)v12;
          *a4 = v14;
        }
      }
      else
      {
        v10 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
            0,
            -2147024882);
      }
    }
  }
  else
  {
    v10 = -2147467261;
    MFTraceError(
      "avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp",
      763,
      "ProfileRegReadValue",
      0,
      -2147467261,
      1);
  }
  return v10;
}

```

## disassembly

```asm
0x180041074  mov     rax, rsp
0x180041077  push    rbx
0x180041078  push    rbp
0x180041079  push    rsi
0x18004107a  push    rdi
0x18004107b  push    r14
0x18004107d  push    r15
0x18004107f  sub     rsp, 48h
0x180041083  mov     dword ptr [rax+8], 0
0x18004108a  mov     rsi, r9
0x18004108d  lea     rax, [rcx-1]
0x180041091  mov     r14, r8
0x180041094  mov     rbp, rdx
0x180041097  mov     r15, rcx
0x18004109a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004109e  ja      loc_180041212
0x1800410a4  test    r8, r8
0x1800410a7  jz      loc_1800411FA
0x1800410ad  test    r9, r9
0x1800410b0  jz      loc_1800411FA
0x1800410b6  test    rdx, rdx
0x1800410b9  jnz     short loc_1800410C5
0x1800410bb  mov     edx, 2FCh
0x1800410c0  jmp     loc_180041217
0x1800410c5  mov     qword ptr [r8], 0
0x1800410cc  lea     rax, [rsp+78h+arg_0]
0x1800410d4  mov     [rsp+78h+pcbData], rax; pcbData
0x1800410d9  mov     r8, rbp; lpValue
0x1800410dc  mov     dword ptr [r9], 0
0x1800410e3  xor     edx, edx; lpSubKey
0x1800410e5  mov     [rsp+78h+pvData], 0; pvData
0x1800410ee  mov     r9d, 2; dwFlags
0x1800410f4  mov     [rsp+78h+pdwType], 0; pdwType
0x1800410fd  call    cs:__imp_RegGetValueW
0x180041103  mov     ebx, eax
0x180041105  test    eax, eax
0x180041107  jz      short loc_18004112A
0x180041109  jle     short loc_180041114
0x18004110b  movzx   ebx, ax
0x18004110e  or      ebx, 80070000h
0x180041114  mov     dword ptr [rsp+78h+pvData], 1
0x18004111c  mov     edx, 306h
0x180041121  mov     dword ptr [rsp+78h+pdwType], ebx
0x180041125  jmp     loc_18004122A
0x18004112a  mov     ecx, [rsp+78h+arg_0]; unsigned __int64
0x180041131  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180041136  mov     rdi, rax
0x180041139  test    rax, rax
0x18004113c  jnz     short loc_180041176
0x18004113e  mov     ebx, 8007000Eh
0x180041143  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004114a  jb      loc_180041241
0x180041150  mov     rcx, cs:WPP_GLOBAL_Control
0x180041157  lea     edx, [rax+44h]
0x18004115a  xor     r9d, r9d
0x18004115d  mov     dword ptr [rsp+78h+pdwType], ebx
0x180041161  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180041168  mov     rcx, [rcx+10h]
0x18004116c  call    WPP_SF_qD
0x180041171  jmp     loc_180041241
0x180041176  lea     rax, [rsp+78h+arg_0]
0x18004117e  mov     r9d, 2; dwFlags
0x180041184  mov     [rsp+78h+pcbData], rax; pcbData
0x180041189  mov     r8, rbp; lpValue
0x18004118c  mov     [rsp+78h+pvData], rdi; pvData
0x180041191  xor     edx, edx; lpSubKey
0x180041193  mov     rcx, r15; hkey
0x180041196  mov     [rsp+78h+pdwType], 0; pdwType
0x18004119f  call    cs:__imp_RegGetValueW
0x1800411a5  mov     ebx, eax
0x1800411a7  test    eax, eax
0x1800411a9  jz      short loc_1800411E8
0x1800411ab  jle     short loc_1800411B6
0x1800411ad  movzx   ebx, ax
0x1800411b0  or      ebx, 80070000h
0x1800411b6  mov     dword ptr [rsp+78h+pvData], 1
0x1800411be  lea     r8, aProfileregread; "ProfileRegReadValue"
0x1800411c5  xor     r9d, r9d
0x1800411c8  mov     dword ptr [rsp+78h+pdwType], ebx
0x1800411cc  mov     edx, 310h
0x1800411d1  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x1800411d8  call    cs:__imp_MFTraceError
0x1800411de  mov     rcx, rdi; Block
0x1800411e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800411e6  jmp     short loc_180041241
0x1800411e8  mov     eax, [rsp+78h+arg_0]
0x1800411ef  xor     ebx, ebx
0x1800411f1  shr     eax, 1
0x1800411f3  mov     [r14], rdi
0x1800411f6  mov     [rsi], eax
0x1800411f8  jmp     short loc_180041241
0x1800411fa  mov     ebx, 80004003h
0x1800411ff  mov     dword ptr [rsp+78h+pvData], 1
0x180041207  mov     dword ptr [rsp+78h+pdwType], ebx
0x18004120b  mov     edx, 2FBh
0x180041210  jmp     short loc_18004122A
0x180041212  mov     edx, 2FAh
0x180041217  mov     eax, 80070057h
0x18004121c  mov     dword ptr [rsp+78h+pvData], 1
0x180041224  mov     ebx, eax
0x180041226  mov     dword ptr [rsp+78h+pdwType], eax
0x18004122a  xor     r9d, r9d
0x18004122d  lea     r8, aProfileregread; "ProfileRegReadValue"
0x180041234  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x18004123b  call    cs:__imp_MFTraceError
0x180041241  mov     eax, ebx
0x180041243  add     rsp, 48h
0x180041247  pop     r15
0x180041249  pop     r14
0x18004124b  pop     rdi
0x18004124c  pop     rsi
0x18004124d  pop     rbp
0x18004124e  pop     rbx
0x18004124f  retn
```
