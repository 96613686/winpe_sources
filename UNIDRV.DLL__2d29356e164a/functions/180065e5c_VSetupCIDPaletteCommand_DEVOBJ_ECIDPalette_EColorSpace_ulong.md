# VSetupCIDPaletteCommand(_DEVOBJ *,ECIDPalette,EColorSpace,ulong)

- ea: `0x180065e5c`
- end: `0x180065fd3`
- name: `?VSetupCIDPaletteCommand@@YAXPEAU_DEVOBJ@@W4ECIDPalette@@W4EColorSpace@@K@Z`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800391b0`
- `0x180067620`

## callees

- `0x180032728`
- `0x180032f50`
- `0x1800487e0`
- `0x180065bf0`
- `0x180065e5c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180065e95`
- `KERNEL32!SetLastError` at `0x180065e95`

## pseudocode

```c
void __fastcall VSetupCIDPaletteCommand(__int64 a1, int a2, char a3, int a4)
{
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  unsigned int v10; // eax
  int v11; // r9d
  _BYTE v12[6]; // [rsp+30h] [rbp-50h]
  int v13; // [rsp+40h] [rbp-40h] BYREF
  __int16 v14; // [rsp+44h] [rbp-3Ch]
  unsigned __int8 v15[32]; // [rsp+50h] [rbp-30h] BYREF

  *(_DWORD *)v12 = 0;
  if ( !a1 )
  {
    SetLastError(0xDu);
    return;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 4464LL) )
  {
    v6 = a4 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 && (unsigned int)(v9 - 1) > 1 )
          {
LABEL_14:
            *(_WORD *)&v12[3] = 2056;
            v12[5] = 8;
            if ( a2 != 1 )
            {
              switch ( a2 )
              {
                case 5:
                  v12[0] = a3;
                  v11 = 5;
                  *(_WORD *)&v12[1] = 2049;
                  break;
                case 6:
                  v11 = 6;
                  break;
                case 7:
                  v11 = 7;
                  break;
                case 8:
                  v10 = iDrvPrintfSafeA(v15, 32, "\x1B&p%di6c%dS", 8, 8);
LABEL_28:
                  PCL_Output((struct _DEVOBJ *)a1, v15, v10);
                  if ( a2 != 1 )
                  {
                    v13 = *(_DWORD *)v12;
                    v14 = *(_WORD *)&v12[4];
                    SendCIDCommand(a1, &v13);
                  }
                  return;
                case 9:
                  v11 = 9;
                  break;
                default:
                  v10 = 0;
                  goto LABEL_28;
              }
              v10 = iDrvPrintfSafeA(v15, 32, "\x1B&p%di6c%dS", v11, v11);
              goto LABEL_28;
            }
            v10 = iDrvPrintfSafeA(v15, 32, "\x1B&p%di6c%dS", 1, 1);
            goto LABEL_28;
          }
          *(_WORD *)&v12[1] = 2051;
        }
        else
        {
          *(_WORD *)&v12[1] = 2049;
        }
      }
      else
      {
        *(_WORD *)&v12[1] = 1025;
      }
    }
    else
    {
      *(_WORD *)&v12[1] = 257;
    }
    v12[0] = a3;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x180065e5c  mov     [rsp-8+arg_8], rbx
0x180065e61  mov     [rsp-8+arg_18], rdi
0x180065e66  push    rbp
0x180065e67  mov     rbp, rsp
0x180065e6a  sub     rsp, 80h
0x180065e71  mov     rax, cs:__security_cookie
0x180065e78  xor     rax, rsp
0x180065e7b  mov     [rbp+var_10], rax
0x180065e7f  xor     eax, eax
0x180065e81  mov     edi, edx
0x180065e83  mov     [rbp+var_50], eax
0x180065e86  mov     rbx, rcx
0x180065e89  mov     [rbp+var_4C], ax
0x180065e8d  test    rcx, rcx
0x180065e90  jnz     short loc_180065EA0
0x180065e92  lea     ecx, [rbx+0Dh]; dwErrCode
0x180065e95  call    cs:__imp_SetLastError
0x180065e9b  jmp     loc_180065FB2
0x180065ea0  mov     rax, [rcx+8]
0x180065ea4  cmp     dword ptr [rax+1170h], 0
0x180065eab  jz      loc_180065FB2
0x180065eb1  mov     edx, 8
0x180065eb6  sub     r9d, 1
0x180065eba  jz      short loc_180065EF2
0x180065ebc  sub     r9d, 1
0x180065ec0  jz      short loc_180065EEA
0x180065ec2  sub     r9d, 1
0x180065ec6  jz      short loc_180065EE2
0x180065ec8  sub     r9d, 1
0x180065ecc  jz      short loc_180065EDA
0x180065ece  sub     r9d, 1
0x180065ed2  jz      short loc_180065EDA
0x180065ed4  cmp     r9d, 1
0x180065ed8  jnz     short loc_180065EFC
0x180065eda  mov     word ptr [rbp+var_50+1], 803h
0x180065ee0  jmp     short loc_180065EF8
0x180065ee2  mov     word ptr [rbp+var_50+1], 801h
0x180065ee8  jmp     short loc_180065EF8
0x180065eea  mov     word ptr [rbp+var_50+1], 401h
0x180065ef0  jmp     short loc_180065EF8
0x180065ef2  mov     word ptr [rbp+var_50+1], 101h
0x180065ef8  mov     byte ptr [rbp+var_50], r8b
0x180065efc  mov     ecx, edi
0x180065efe  mov     word ptr [rbp+var_50+3], 808h
0x180065f04  mov     byte ptr [rbp+var_4C+1], dl
0x180065f07  sub     ecx, 1
0x180065f0a  jz      short loc_180065F61
0x180065f0c  sub     ecx, 4
0x180065f0f  jz      short loc_180065F4F
0x180065f11  sub     ecx, 1
0x180065f14  jz      short loc_180065F47
0x180065f16  sub     ecx, 1
0x180065f19  jz      short loc_180065F3F
0x180065f1b  sub     ecx, 1
0x180065f1e  jz      short loc_180065F36
0x180065f20  cmp     ecx, 1
0x180065f23  jz      short loc_180065F29
0x180065f25  xor     eax, eax
0x180065f27  jmp     short loc_180065F84
0x180065f29  mov     r9d, 9
0x180065f2f  mov     [rsp+80h+var_60], r9d
0x180065f34  jmp     short loc_180065F6F
0x180065f36  mov     [rsp+80h+var_60], edx
0x180065f3a  mov     r9d, edx
0x180065f3d  jmp     short loc_180065F6F
0x180065f3f  mov     r9d, 7
0x180065f45  jmp     short loc_180065F2F
0x180065f47  mov     r9d, 6
0x180065f4d  jmp     short loc_180065F2F
0x180065f4f  mov     byte ptr [rbp+var_50], r8b
0x180065f53  mov     r9d, 5
0x180065f59  mov     word ptr [rbp+var_50+1], 801h
0x180065f5f  jmp     short loc_180065F2F
0x180065f61  mov     [rsp+80h+var_60], 1
0x180065f69  mov     r9d, 1
0x180065f6f  lea     r8, aPDi6cDs; "\x1B&p%di6c%dS"
0x180065f76  mov     edx, 20h ; ' '
0x180065f7b  lea     rcx, [rbp+var_30]
0x180065f7f  call    iDrvPrintfSafeA
0x180065f84  mov     r8d, eax; unsigned int
0x180065f87  lea     rdx, [rbp+var_30]; unsigned __int8 *
0x180065f8b  mov     rcx, rbx; struct _DEVOBJ *
0x180065f8e  call    ?PCL_Output@@YAHPEAU_DEVOBJ@@PEAXK@Z; PCL_Output(_DEVOBJ *,void *,ulong)
0x180065f93  cmp     edi, 1
0x180065f96  jz      short loc_180065FB2
0x180065f98  mov     eax, [rbp+var_50]
0x180065f9b  lea     rdx, [rbp+var_40]
0x180065f9f  mov     [rbp+var_40], eax
0x180065fa2  mov     rcx, rbx
0x180065fa5  movzx   eax, [rbp+var_4C]
0x180065fa9  mov     [rbp+var_3C], ax
0x180065fad  call    ?SendCIDCommand@@YAHPEAU_DEVOBJ@@U_CIDSHORT@@W4ECIDFormat@@@Z; SendCIDCommand(_DEVOBJ *,_CIDSHORT,ECIDFormat)
0x180065fb2  mov     rcx, [rbp+var_10]
0x180065fb6  xor     rcx, rsp; StackCookie
0x180065fb9  call    __security_check_cookie
0x180065fbe  lea     r11, [rsp+80h+var_s0]
0x180065fc6  mov     rbx, [r11+18h]
0x180065fca  mov     rdi, [r11+28h]
0x180065fce  mov     rsp, r11
0x180065fd1  pop     rbp
0x180065fd2  retn
```
