# SystemSettings::IsOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint)

- ea: `0x180025d64`
- end: `0x180025e03`
- name: `?IsOn@SystemSettings@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020dfc`

## callees

- `0x180025d64`
- `0x18002d220`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180025ddc`
- `USER32!SystemParametersInfoW` at `0x180025ddc`

## pseudocode

```c
__int64 __fastcall SystemSettings::IsOn(_QWORD *a1, unsigned int a2)
{
  __int64 v2; // r10
  unsigned __int16 *v3; // rax
  __int64 v4; // r8
  int v5; // edx
  int v6; // ecx
  UINT v7; // edx
  UINT v8; // ecx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-58h] BYREF

  v2 = 32LL * a2;
  v3 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v2);
  v4 = *a1 - (_QWORD)v3;
  do
  {
    v5 = *(unsigned __int16 *)((char *)v3 + v4);
    v6 = *v3 - v5;
    if ( v6 )
      break;
    ++v3;
  }
  while ( v5 );
  if ( !v6
    && *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 16) == 2
    && (v7 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 20),
        v8 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 8),
        memset(pvParam, 0, 60),
        LODWORD(pvParam[0]) = v7,
        SystemParametersInfoW(v8, v7, pvParam, 0)) )
  {
    return BYTE4(pvParam[0]) & 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180025d64  sub     rsp, 78h
0x180025d68  mov     rax, cs:__security_cookie
0x180025d6f  xor     rax, rsp
0x180025d72  mov     [rsp+78h+var_18], rax
0x180025d77  mov     r8, [rcx]
0x180025d7a  lea     r11, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x180025d81  mov     r10d, edx
0x180025d84  shl     r10, 5
0x180025d88  mov     rax, [r10+r11]
0x180025d8c  sub     r8, rax
0x180025d8f  movzx   ecx, word ptr [rax]
0x180025d92  movzx   edx, word ptr [rax+r8]
0x180025d97  sub     ecx, edx
0x180025d99  jnz     short loc_180025DA3
0x180025d9b  add     rax, 2
0x180025d9f  test    edx, edx
0x180025da1  jnz     short loc_180025D8F
0x180025da3  test    ecx, ecx
0x180025da5  jnz     short loc_180025DEF
0x180025da7  cmp     dword ptr [r10+r11+10h], 2
0x180025dad  jnz     short loc_180025DEF
0x180025daf  mov     edx, [r10+r11+14h]; uiParam
0x180025db4  lea     r8, [rsp+78h+pvParam]; pvParam
0x180025db9  mov     ecx, [r10+r11+8]; uiAction
0x180025dbe  xorps   xmm0, xmm0
0x180025dc1  movups  [rsp+78h+pvParam], xmm0
0x180025dc6  xor     r9d, r9d; fWinIni
0x180025dc9  mov     dword ptr [rsp+78h+pvParam], edx
0x180025dcd  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x180025dd2  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x180025dd7  movups  [rsp+78h+var_48], xmm0
0x180025ddc  call    cs:__imp_SystemParametersInfoW
0x180025de2  test    eax, eax
0x180025de4  jz      short loc_180025DEF
0x180025de6  mov     eax, dword ptr [rsp+78h+pvParam+4]
0x180025dea  and     eax, 1
0x180025ded  jmp     short loc_180025DF1
0x180025def  xor     eax, eax
0x180025df1  mov     rcx, [rsp+78h+var_18]
0x180025df6  xor     rcx, rsp; StackCookie
0x180025df9  call    __security_check_cookie
0x180025dfe  add     rsp, 78h
0x180025e02  retn
```
