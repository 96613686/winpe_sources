# VSetupCIDPaletteCommand(_DEVOBJ *,ECIDPalette,EColorSpace,ulong)

- ea: `0x1800675fc`
- end: `0x18006777a`
- name: `?VSetupCIDPaletteCommand@@YAXPEAU_DEVOBJ@@W4ECIDPalette@@W4EColorSpace@@K@Z`
- size: `382`
- prototype: `void __fastcall(__int64, int, char, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039c20`
- `0x180068e40`

## callees

- `0x180033050`
- `0x1800338d4`
- `0x180049d00`
- `0x180067338`
- `0x1800675fc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180067635`
- `KERNEL32!SetLastError` at `0x180067635`

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
                  v10 = iDrvPrintfSafeA((__int64)v15, 32, (__int64)"\x1B&p%di6c%dS", 8, 8);
LABEL_28:
                  PCL_Output((struct _DEVOBJ *)a1, v15, v10);
                  if ( a2 != 1 )
                  {
                    v13 = *(_DWORD *)v12;
                    v14 = *(_WORD *)&v12[4];
                    SendCIDCommand((struct _DEVOBJ *)a1, (unsigned __int8 *)&v13);
                  }
                  return;
                case 9:
                  v11 = 9;
                  break;
                default:
                  v10 = 0;
                  goto LABEL_28;
              }
              v10 = iDrvPrintfSafeA((__int64)v15, 32, (__int64)"\x1B&p%di6c%dS", v11, v11);
              goto LABEL_28;
            }
            v10 = iDrvPrintfSafeA((__int64)v15, 32, (__int64)"\x1B&p%di6c%dS", 1, 1);
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
0x1800675fc  mov     [rsp-8+arg_8], rbx
0x180067601  mov     [rsp-8+arg_18], rdi
0x180067606  push    rbp
0x180067607  mov     rbp, rsp
0x18006760a  sub     rsp, 80h
0x180067611  mov     rax, cs:__security_cookie
0x180067618  xor     rax, rsp
0x18006761b  mov     [rbp+var_10], rax
0x18006761f  xor     eax, eax
0x180067621  mov     edi, edx
0x180067623  mov     [rbp+var_50], eax
0x180067626  mov     rbx, rcx
0x180067629  mov     [rbp+var_4C], ax
0x18006762d  test    rcx, rcx
0x180067630  jnz     short loc_180067646
0x180067632  lea     ecx, [rbx+0Dh]; dwErrCode
0x180067635  call    cs:__imp_SetLastError
0x18006763c  nop     dword ptr [rax+rax+00h]
0x180067641  jmp     loc_180067758
0x180067646  mov     rax, [rcx+8]
0x18006764a  cmp     dword ptr [rax+1170h], 0
0x180067651  jz      loc_180067758
0x180067657  mov     edx, 8
0x18006765c  sub     r9d, 1
0x180067660  jz      short loc_180067698
0x180067662  sub     r9d, 1
0x180067666  jz      short loc_180067690
0x180067668  sub     r9d, 1
0x18006766c  jz      short loc_180067688
0x18006766e  sub     r9d, 1
0x180067672  jz      short loc_180067680
0x180067674  sub     r9d, 1
0x180067678  jz      short loc_180067680
0x18006767a  cmp     r9d, 1
0x18006767e  jnz     short loc_1800676A2
0x180067680  mov     word ptr [rbp+var_50+1], 803h
0x180067686  jmp     short loc_18006769E
0x180067688  mov     word ptr [rbp+var_50+1], 801h
0x18006768e  jmp     short loc_18006769E
0x180067690  mov     word ptr [rbp+var_50+1], 401h
0x180067696  jmp     short loc_18006769E
0x180067698  mov     word ptr [rbp+var_50+1], 101h
0x18006769e  mov     byte ptr [rbp+var_50], r8b
0x1800676a2  mov     ecx, edi
0x1800676a4  mov     word ptr [rbp+var_50+3], 808h
0x1800676aa  mov     byte ptr [rbp+var_4C+1], dl
0x1800676ad  sub     ecx, 1
0x1800676b0  jz      short loc_180067707
0x1800676b2  sub     ecx, 4
0x1800676b5  jz      short loc_1800676F5
0x1800676b7  sub     ecx, 1
0x1800676ba  jz      short loc_1800676ED
0x1800676bc  sub     ecx, 1
0x1800676bf  jz      short loc_1800676E5
0x1800676c1  sub     ecx, 1
0x1800676c4  jz      short loc_1800676DC
0x1800676c6  cmp     ecx, 1
0x1800676c9  jz      short loc_1800676CF
0x1800676cb  xor     eax, eax
0x1800676cd  jmp     short loc_18006772A
0x1800676cf  mov     r9d, 9
0x1800676d5  mov     [rsp+80h+var_60], r9d
0x1800676da  jmp     short loc_180067715
0x1800676dc  mov     [rsp+80h+var_60], edx
0x1800676e0  mov     r9d, edx
0x1800676e3  jmp     short loc_180067715
0x1800676e5  mov     r9d, 7
0x1800676eb  jmp     short loc_1800676D5
0x1800676ed  mov     r9d, 6
0x1800676f3  jmp     short loc_1800676D5
0x1800676f5  mov     byte ptr [rbp+var_50], r8b
0x1800676f9  mov     r9d, 5
0x1800676ff  mov     word ptr [rbp+var_50+1], 801h
0x180067705  jmp     short loc_1800676D5
0x180067707  mov     [rsp+80h+var_60], 1
0x18006770f  mov     r9d, 1
0x180067715  lea     r8, aPDi6cDs; "\x1B&p%di6c%dS"
0x18006771c  mov     edx, 20h ; ' '
0x180067721  lea     rcx, [rbp+var_30]
0x180067725  call    iDrvPrintfSafeA
0x18006772a  mov     r8d, eax; unsigned int
0x18006772d  lea     rdx, [rbp+var_30]; unsigned __int8 *
0x180067731  mov     rcx, rbx; struct _DEVOBJ *
0x180067734  call    ?PCL_Output@@YAHPEAU_DEVOBJ@@PEAXK@Z; PCL_Output(_DEVOBJ *,void *,ulong)
0x180067739  cmp     edi, 1
0x18006773c  jz      short loc_180067758
0x18006773e  mov     eax, [rbp+var_50]
0x180067741  lea     rdx, [rbp+var_40]
0x180067745  mov     [rbp+var_40], eax
0x180067748  mov     rcx, rbx
0x18006774b  movzx   eax, [rbp+var_4C]
0x18006774f  mov     [rbp+var_3C], ax
0x180067753  call    ?SendCIDCommand@@YAHPEAU_DEVOBJ@@U_CIDSHORT@@W4ECIDFormat@@@Z; SendCIDCommand(_DEVOBJ *,_CIDSHORT,ECIDFormat)
0x180067758  mov     rcx, [rbp+var_10]
0x18006775c  xor     rcx, rsp; StackCookie
0x18006775f  call    __security_check_cookie
0x180067764  lea     r11, [rsp+80h+var_s0]
0x18006776c  mov     rbx, [r11+18h]
0x180067770  mov     rdi, [r11+28h]
0x180067774  mov     rsp, r11
0x180067777  pop     rbp
0x180067778  retn
```
