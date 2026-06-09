# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x180025fdc`
- end: `0x180026188`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800241b0`

## callees

- `0x180025c78`
- `0x180025e0c`
- `0x180025fdc`
- `0x18002d1fa`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026174`
- `USER32!SendNotifyMessageW` at `0x180026120`
- `USER32!SendNotifyMessageW` at `0x180026120`
- `USER32!SystemParametersInfoW` at `0x1800260c0`
- `USER32!SystemParametersInfoW` at `0x180026106`
- `USER32!SystemParametersInfoW` at `0x18002616a`
- `USER32!SystemParametersInfoW` at `0x1800260c0`
- `USER32!SystemParametersInfoW` at `0x180026106`
- `USER32!SystemParametersInfoW` at `0x18002616a`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOn(_QWORD *a1, unsigned int a2, UINT *a3, int a4)
{
  __int64 v6; // rbx
  UINT v7; // esi
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  int v10; // ecx
  int v11; // edx
  signed int result; // eax
  int v13; // ecx
  int v14; // ecx
  UINT v15; // eax
  UINT v16; // ecx
  bool v17; // zf
  UINT *v18; // r8
  UINT v19; // edx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-68h] BYREF

  v6 = 32LL * a2;
  v7 = a4 != 0 ? 3 : 0;
  v8 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v6);
  v9 = *a1 - (_QWORD)v8;
  do
  {
    v10 = *(unsigned __int16 *)((char *)v8 + v9);
    v11 = *v8 - v10;
    if ( v11 )
      break;
    ++v8;
  }
  while ( v10 );
  if ( v11 )
    return -2147024809;
  if ( wcscmp_0(*(const wchar_t **)((char *)&SystemSettings::_systemSetting + v6), L"animations")
    || (result = SystemSettings::SetAdditionalAnimationSetting((PVOID)*a3), result >= 0) )
  {
    v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 16);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          return 0;
        v15 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
        if ( !a3 )
        {
          v16 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 8);
          memset(pvParam, 0, 60);
          LODWORD(pvParam[0]) = v15;
          if ( SystemParametersInfoW(v16, v15, pvParam, 0) )
          {
            if ( (BYTE4(pvParam[0]) & 1) == 0 )
            {
              v17 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12) == 67;
              DWORD1(pvParam[0]) |= 1u;
              if ( v17 && IsInMachineOOBEOrLogonUI() )
                DWORD1(pvParam[0]) |= 0x1000u;
              SystemParametersInfoW(
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20),
                pvParam,
                v7);
              if ( !a4 )
                SendNotifyMessageW(
                  HWND_BROADCAST,
                  0x1Au,
                  *(unsigned int *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                  0);
            }
            return 0;
          }
          goto LABEL_26;
        }
        *a3 = v15;
        v18 = a3;
      }
      else
      {
        v18 = (UINT *)(int)*a3;
      }
      v19 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
    }
    else
    {
      v18 = *(UINT **)((char *)&SystemSettings::_systemSetting + v6 + 24);
      v19 = *a3;
    }
    if ( !SystemParametersInfoW(*(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12), v19, v18, v7) )
    {
LABEL_26:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025fdc  mov     [rsp+arg_0], rbx
0x180025fe1  mov     [rsp+arg_18], rbp
0x180025fe6  push    rsi
0x180025fe7  push    rdi
0x180025fe8  push    r14
0x180025fea  sub     rsp, 70h
0x180025fee  mov     rax, cs:__security_cookie
0x180025ff5  xor     rax, rsp
0x180025ff8  mov     [rsp+88h+var_28], rax
0x180025ffd  mov     eax, r9d
0x180026000  mov     ebx, edx
0x180026002  neg     eax
0x180026004  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x18002600b  mov     rdi, r8
0x18002600e  mov     ebp, r9d
0x180026011  mov     r8, [rcx]
0x180026014  sbb     esi, esi
0x180026016  shl     rbx, 5
0x18002601a  and     esi, 3
0x18002601d  mov     rax, [rbx+r14]
0x180026021  sub     r8, rax
0x180026024  movzx   edx, word ptr [rax]
0x180026027  movzx   ecx, word ptr [rax+r8]
0x18002602c  sub     edx, ecx
0x18002602e  jnz     short loc_180026038
0x180026030  add     rax, 2
0x180026034  test    ecx, ecx
0x180026036  jnz     short loc_180026024
0x180026038  test    edx, edx
0x18002603a  jz      short loc_180026046
0x18002603c  mov     eax, 80070057h
0x180026041  jmp     loc_180026128
0x180026046  mov     rcx, [rbx+r14]; String1
0x18002604a  lea     rdx, aAnimations; "animations"
0x180026051  call    wcscmp_0
0x180026056  test    eax, eax
0x180026058  jnz     short loc_180026069
0x18002605a  mov     ecx, [rdi]; pvParam
0x18002605c  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x180026061  test    eax, eax
0x180026063  js      loc_180026128
0x180026069  mov     ecx, [rbx+r14+10h]
0x18002606e  test    ecx, ecx
0x180026070  jz      loc_18002615B
0x180026076  sub     ecx, 1
0x180026079  jz      loc_180026156
0x18002607f  cmp     ecx, 1
0x180026082  jnz     loc_180026126
0x180026088  mov     eax, [rbx+r14+14h]
0x18002608d  test    rdi, rdi
0x180026090  jnz     loc_18002614A
0x180026096  mov     ecx, [rbx+r14+8]; uiAction
0x18002609b  lea     r8, [rsp+88h+pvParam]; pvParam
0x1800260a0  xorps   xmm0, xmm0
0x1800260a3  xor     r9d, r9d; fWinIni
0x1800260a6  movups  [rsp+88h+pvParam], xmm0
0x1800260ab  mov     edx, eax; uiParam
0x1800260ad  mov     dword ptr [rsp+88h+pvParam], eax
0x1800260b1  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x1800260b6  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x1800260bb  movups  [rsp+88h+var_58], xmm0
0x1800260c0  call    cs:__imp_SystemParametersInfoW
0x1800260c6  test    eax, eax
0x1800260c8  jz      loc_180026174
0x1800260ce  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x1800260d2  test    al, 1
0x1800260d4  jnz     short loc_180026126
0x1800260d6  or      eax, 1
0x1800260d9  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x1800260df  mov     dword ptr [rsp+88h+pvParam+4], eax
0x1800260e3  jnz     short loc_1800260F4
0x1800260e5  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x1800260ea  test    al, al
0x1800260ec  jz      short loc_1800260F4
0x1800260ee  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x1800260f4  mov     edx, [rbx+r14+14h]; uiParam
0x1800260f9  lea     r8, [rsp+88h+pvParam]; pvParam
0x1800260fe  mov     ecx, [rbx+r14+0Ch]; uiAction
0x180026103  mov     r9d, esi; fWinIni
0x180026106  call    cs:__imp_SystemParametersInfoW
0x18002610c  test    ebp, ebp
0x18002610e  jnz     short loc_180026126
0x180026110  mov     r8d, [rbx+r14+0Ch]; wParam
0x180026115  lea     edx, [rbp+1Ah]; Msg
0x180026118  xor     r9d, r9d; lParam
0x18002611b  mov     ecx, 0FFFFh; hWnd
0x180026120  call    cs:__imp_SendNotifyMessageW
0x180026126  xor     eax, eax
0x180026128  mov     rcx, [rsp+88h+var_28]
0x18002612d  xor     rcx, rsp; StackCookie
0x180026130  call    __security_check_cookie
0x180026135  lea     r11, [rsp+88h+var_18]
0x18002613a  mov     rbx, [r11+20h]
0x18002613e  mov     rbp, [r11+38h]
0x180026142  mov     rsp, r11
0x180026145  pop     r14
0x180026147  pop     rdi
0x180026148  pop     rsi
0x180026149  retn
0x18002614a  mov     [rdi], eax
0x18002614c  mov     r8, rdi
0x18002614f  mov     edx, [rbx+r14+14h]
0x180026154  jmp     short loc_180026162
0x180026156  movsxd  r8, dword ptr [rdi]
0x180026159  jmp     short loc_18002614F
0x18002615b  mov     r8, [rbx+r14+18h]; pvParam
0x180026160  mov     edx, [rdi]; uiParam
0x180026162  mov     ecx, [rbx+r14+0Ch]; uiAction
0x180026167  mov     r9d, esi; fWinIni
0x18002616a  call    cs:__imp_SystemParametersInfoW
0x180026170  test    eax, eax
0x180026172  jnz     short loc_180026126
0x180026174  call    cs:__imp_GetLastError
0x18002617a  test    eax, eax
0x18002617c  jle     short loc_180026128
0x18002617e  movzx   eax, ax
0x180026181  or      eax, 80070000h
0x180026186  jmp     short loc_180026128
```
