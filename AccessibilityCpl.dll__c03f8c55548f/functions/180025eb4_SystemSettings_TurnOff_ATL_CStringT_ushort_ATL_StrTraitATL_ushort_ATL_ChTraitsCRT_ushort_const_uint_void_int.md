# SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x180025eb4`
- end: `0x180025fd3`
- name: `?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800245c8`

## callees

- `0x180025c78`
- `0x180025eb4`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f52`
- `USER32!SendNotifyMessageW` at `0x180025fb5`
- `USER32!SendNotifyMessageW` at `0x180025fb5`
- `USER32!SystemParametersInfoW` at `0x180025f48`
- `USER32!SystemParametersInfoW` at `0x180025f9b`
- `USER32!SystemParametersInfoW` at `0x180025f48`
- `USER32!SystemParametersInfoW` at `0x180025f9b`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOff(_QWORD *a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 v5; // rbx
  UINT v6; // edi
  unsigned __int16 *v7; // rax
  __int64 v8; // r8
  int v9; // ecx
  int v10; // edx
  signed int result; // eax
  UINT v12; // edx
  UINT v13; // ecx
  bool v14; // zf
  _OWORD pvParam[4]; // [rsp+20h] [rbp-78h] BYREF

  v5 = 32LL * a2;
  v6 = a4 != 0 ? 3 : 0;
  v7 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v5);
  v8 = *a1 - (_QWORD)v7;
  do
  {
    v9 = *(unsigned __int16 *)((char *)v7 + v8);
    v10 = *v7 - v9;
    if ( v10 )
      break;
    ++v7;
  }
  while ( v9 );
  if ( v10 )
    return -2147024809;
  if ( *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 16) != 2 )
    return 0;
  v12 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20);
  v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 8);
  memset(pvParam, 0, 60);
  LODWORD(pvParam[0]) = v12;
  if ( SystemParametersInfoW(v13, v12, pvParam, 0) )
  {
    if ( (BYTE4(pvParam[0]) & 1) != 0 )
    {
      v14 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12) == 67;
      DWORD1(pvParam[0]) &= ~1u;
      if ( v14 && IsInMachineOOBEOrLogonUI() )
        DWORD1(pvParam[0]) |= 0x1000u;
      SystemParametersInfoW(
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12),
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20),
        pvParam,
        v6);
      if ( !a4 )
        SendNotifyMessageW(
          HWND_BROADCAST,
          0x1Au,
          *(unsigned int *)((char *)&SystemSettings::_systemSetting + v5 + 12),
          0);
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025eb4  push    rbx
0x180025eb6  push    rbp
0x180025eb7  push    rsi
0x180025eb8  push    rdi
0x180025eb9  sub     rsp, 78h
0x180025ebd  mov     rax, cs:__security_cookie
0x180025ec4  xor     rax, rsp
0x180025ec7  mov     [rsp+98h+var_38], rax
0x180025ecc  mov     r8, [rcx]
0x180025ecf  lea     rbp, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x180025ed6  mov     eax, r9d
0x180025ed9  mov     ebx, edx
0x180025edb  neg     eax
0x180025edd  mov     esi, r9d
0x180025ee0  sbb     edi, edi
0x180025ee2  shl     rbx, 5
0x180025ee6  and     edi, 3
0x180025ee9  mov     rax, [rbx+rbp]
0x180025eed  sub     r8, rax
0x180025ef0  movzx   edx, word ptr [rax]
0x180025ef3  movzx   ecx, word ptr [rax+r8]
0x180025ef8  sub     edx, ecx
0x180025efa  jnz     short loc_180025F04
0x180025efc  add     rax, 2
0x180025f00  test    ecx, ecx
0x180025f02  jnz     short loc_180025EF0
0x180025f04  test    edx, edx
0x180025f06  jz      short loc_180025F12
0x180025f08  mov     eax, 80070057h
0x180025f0d  jmp     loc_180025FBD
0x180025f12  cmp     dword ptr [rbx+rbp+10h], 2
0x180025f17  jnz     loc_180025FBB
0x180025f1d  mov     edx, [rbx+rbp+14h]; uiParam
0x180025f21  lea     r8, [rsp+98h+pvParam]; pvParam
0x180025f26  mov     ecx, [rbx+rbp+8]; uiAction
0x180025f2a  xorps   xmm0, xmm0
0x180025f2d  movups  [rsp+98h+pvParam], xmm0
0x180025f32  xor     r9d, r9d; fWinIni
0x180025f35  mov     dword ptr [rsp+98h+pvParam], edx
0x180025f39  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x180025f3e  movups  xmmword ptr [rsp+98h+var_58+0Ch], xmm0
0x180025f43  movups  [rsp+98h+var_68], xmm0
0x180025f48  call    cs:__imp_SystemParametersInfoW
0x180025f4e  test    eax, eax
0x180025f50  jnz     short loc_180025F66
0x180025f52  call    cs:__imp_GetLastError
0x180025f58  test    eax, eax
0x180025f5a  jle     short loc_180025FBD
0x180025f5c  movzx   eax, ax
0x180025f5f  or      eax, 80070000h
0x180025f64  jmp     short loc_180025FBD
0x180025f66  mov     eax, dword ptr [rsp+98h+pvParam+4]
0x180025f6a  test    al, 1
0x180025f6c  jz      short loc_180025FBB
0x180025f6e  and     eax, 0FFFFFFFEh
0x180025f71  cmp     dword ptr [rbx+rbp+0Ch], 43h ; 'C'
0x180025f76  mov     dword ptr [rsp+98h+pvParam+4], eax
0x180025f7a  jnz     short loc_180025F8B
0x180025f7c  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x180025f81  test    al, al
0x180025f83  jz      short loc_180025F8B
0x180025f85  bts     dword ptr [rsp+98h+pvParam+4], 0Ch
0x180025f8b  mov     edx, [rbx+rbp+14h]; uiParam
0x180025f8f  lea     r8, [rsp+98h+pvParam]; pvParam
0x180025f94  mov     ecx, [rbx+rbp+0Ch]; uiAction
0x180025f98  mov     r9d, edi; fWinIni
0x180025f9b  call    cs:__imp_SystemParametersInfoW
0x180025fa1  test    esi, esi
0x180025fa3  jnz     short loc_180025FBB
0x180025fa5  mov     r8d, [rbx+rbp+0Ch]; wParam
0x180025faa  lea     edx, [rsi+1Ah]; Msg
0x180025fad  xor     r9d, r9d; lParam
0x180025fb0  mov     ecx, 0FFFFh; hWnd
0x180025fb5  call    cs:__imp_SendNotifyMessageW
0x180025fbb  xor     eax, eax
0x180025fbd  mov     rcx, [rsp+98h+var_38]
0x180025fc2  xor     rcx, rsp; StackCookie
0x180025fc5  call    __security_check_cookie
0x180025fca  add     rsp, 78h
0x180025fce  pop     rdi
0x180025fcf  pop     rsi
0x180025fd0  pop     rbp
0x180025fd1  pop     rbx
0x180025fd2  retn
```
