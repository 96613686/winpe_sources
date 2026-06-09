# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x140015644`
- end: `0x1400157f0`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010244`

## callees

- `0x1400069b0`
- `0x140015598`
- `0x140015644`
- `0x140015ace`
- `0x140015b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400157dc`
- `KERNEL32!GetLastError` at `0x1400157dc`
- `USER32!SystemParametersInfoW` at `0x140015728`
- `USER32!SystemParametersInfoW` at `0x14001576e`
- `USER32!SystemParametersInfoW` at `0x1400157d2`
- `USER32!SystemParametersInfoW` at `0x140015728`
- `USER32!SystemParametersInfoW` at `0x14001576e`
- `USER32!SystemParametersInfoW` at `0x1400157d2`
- `USER32!SendNotifyMessageW` at `0x140015788`
- `USER32!SendNotifyMessageW` at `0x140015788`

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
0x140015644  mov     [rsp+arg_0], rbx
0x140015649  mov     [rsp+arg_18], rbp
0x14001564e  push    rsi
0x14001564f  push    rdi
0x140015650  push    r14
0x140015652  sub     rsp, 70h
0x140015656  mov     rax, cs:__security_cookie
0x14001565d  xor     rax, rsp
0x140015660  mov     [rsp+88h+var_28], rax
0x140015665  mov     eax, r9d
0x140015668  mov     ebx, edx
0x14001566a  neg     eax
0x14001566c  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x140015673  mov     rdi, r8
0x140015676  mov     ebp, r9d
0x140015679  mov     r8, [rcx]
0x14001567c  sbb     esi, esi
0x14001567e  shl     rbx, 5
0x140015682  and     esi, 3
0x140015685  mov     rax, [rbx+r14]
0x140015689  sub     r8, rax
0x14001568c  movzx   edx, word ptr [rax]
0x14001568f  movzx   ecx, word ptr [rax+r8]
0x140015694  sub     edx, ecx
0x140015696  jnz     short loc_1400156A0
0x140015698  add     rax, 2
0x14001569c  test    ecx, ecx
0x14001569e  jnz     short loc_14001568C
0x1400156a0  test    edx, edx
0x1400156a2  jz      short loc_1400156AE
0x1400156a4  mov     eax, 80070057h
0x1400156a9  jmp     loc_140015790
0x1400156ae  mov     rcx, [rbx+r14]; String1
0x1400156b2  lea     rdx, aAnimations; "animations"
0x1400156b9  call    wcscmp_0
0x1400156be  test    eax, eax
0x1400156c0  jnz     short loc_1400156D1
0x1400156c2  mov     ecx, [rdi]; pvParam
0x1400156c4  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x1400156c9  test    eax, eax
0x1400156cb  js      loc_140015790
0x1400156d1  mov     ecx, [rbx+r14+10h]
0x1400156d6  test    ecx, ecx
0x1400156d8  jz      loc_1400157C3
0x1400156de  sub     ecx, 1
0x1400156e1  jz      loc_1400157BE
0x1400156e7  cmp     ecx, 1
0x1400156ea  jnz     loc_14001578E
0x1400156f0  mov     eax, [rbx+r14+14h]
0x1400156f5  test    rdi, rdi
0x1400156f8  jnz     loc_1400157B2
0x1400156fe  mov     ecx, [rbx+r14+8]; uiAction
0x140015703  lea     r8, [rsp+88h+pvParam]; pvParam
0x140015708  xorps   xmm0, xmm0
0x14001570b  xor     r9d, r9d; fWinIni
0x14001570e  movups  [rsp+88h+pvParam], xmm0
0x140015713  mov     edx, eax; uiParam
0x140015715  mov     dword ptr [rsp+88h+pvParam], eax
0x140015719  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x14001571e  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x140015723  movups  [rsp+88h+var_58], xmm0
0x140015728  call    cs:__imp_SystemParametersInfoW
0x14001572e  test    eax, eax
0x140015730  jz      loc_1400157DC
0x140015736  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x14001573a  test    al, 1
0x14001573c  jnz     short loc_14001578E
0x14001573e  or      eax, 1
0x140015741  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x140015747  mov     dword ptr [rsp+88h+pvParam+4], eax
0x14001574b  jnz     short loc_14001575C
0x14001574d  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x140015752  test    al, al
0x140015754  jz      short loc_14001575C
0x140015756  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x14001575c  mov     edx, [rbx+r14+14h]; uiParam
0x140015761  lea     r8, [rsp+88h+pvParam]; pvParam
0x140015766  mov     ecx, [rbx+r14+0Ch]; uiAction
0x14001576b  mov     r9d, esi; fWinIni
0x14001576e  call    cs:__imp_SystemParametersInfoW
0x140015774  test    ebp, ebp
0x140015776  jnz     short loc_14001578E
0x140015778  mov     r8d, [rbx+r14+0Ch]; wParam
0x14001577d  lea     edx, [rbp+1Ah]; Msg
0x140015780  xor     r9d, r9d; lParam
0x140015783  mov     ecx, 0FFFFh; hWnd
0x140015788  call    cs:__imp_SendNotifyMessageW
0x14001578e  xor     eax, eax
0x140015790  mov     rcx, [rsp+88h+var_28]
0x140015795  xor     rcx, rsp; StackCookie
0x140015798  call    __security_check_cookie
0x14001579d  lea     r11, [rsp+88h+var_18]
0x1400157a2  mov     rbx, [r11+20h]
0x1400157a6  mov     rbp, [r11+38h]
0x1400157aa  mov     rsp, r11
0x1400157ad  pop     r14
0x1400157af  pop     rdi
0x1400157b0  pop     rsi
0x1400157b1  retn
0x1400157b2  mov     [rdi], eax
0x1400157b4  mov     r8, rdi
0x1400157b7  mov     edx, [rbx+r14+14h]
0x1400157bc  jmp     short loc_1400157CA
0x1400157be  movsxd  r8, dword ptr [rdi]
0x1400157c1  jmp     short loc_1400157B7
0x1400157c3  mov     r8, [rbx+r14+18h]; pvParam
0x1400157c8  mov     edx, [rdi]; uiParam
0x1400157ca  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1400157cf  mov     r9d, esi; fWinIni
0x1400157d2  call    cs:__imp_SystemParametersInfoW
0x1400157d8  test    eax, eax
0x1400157da  jnz     short loc_14001578E
0x1400157dc  call    cs:__imp_GetLastError
0x1400157e2  test    eax, eax
0x1400157e4  jle     short loc_140015790
0x1400157e6  movzx   eax, ax
0x1400157e9  or      eax, 80070000h
0x1400157ee  jmp     short loc_140015790
```
