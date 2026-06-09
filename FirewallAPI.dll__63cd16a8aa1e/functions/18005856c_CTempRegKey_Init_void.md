# CTempRegKey::Init(void)

- ea: `0x18005856c`
- end: `0x180058798`
- name: `?Init@CTempRegKey@@QEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CTempRegKey *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025744`
- `0x1800587a0`

## callees

- `0x180005954`
- `0x180018578`
- `0x180023744`
- `0x1800277b0`
- `0x18003104c`
- `0x18005845c`
- `0x18005856c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800585cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800585cf`
- `fwbase!FwRegCreateKey` at `0x180058625`
- `fwbase!FwRegCreateKey` at `0x18005869c`
- `fwbase!FwRegCreateKey` at `0x180058625`
- `fwbase!FwRegCreateKey` at `0x18005869c`
- `fwbase!FwRegCloseKey` at `0x180058776`
- `fwbase!FwRegCloseKey` at `0x180058776`

## pseudocode

```c
__int64 __fastcall CTempRegKey::Init(unsigned __int16 **this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  FwPolicy2 *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  int Key; // eax
  const unsigned __int16 **v8; // rsi
  unsigned __int16 *v9; // rdi
  HKEY phkResult; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  phkResult = 0;
  v2 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
    Key = FwRegCreateKey(phkResult, L"Software\\Microsoft\\Windows Firewall", 983103, this + 2);
    v3 = Key;
    if ( Key >= 0 )
    {
      v8 = (const unsigned __int16 **)(this + 3);
      Key = FwCreateGuidString(this + 3);
      v3 = Key;
      if ( Key >= 0 )
      {
        Key = FwRegCreateKey(this[2], *v8, 983103, this + 1);
        v3 = Key;
        if ( Key >= 0 )
        {
          v9 = (unsigned __int16 *)(this + 4);
          Key = StringCchCopyW(v9, 0x56u, L"Software\\Microsoft\\Windows Firewall");
          v3 = Key;
          if ( Key >= 0 )
          {
            Key = StringCchCatW(v9, 0x56u, L"\\");
            v3 = Key;
            if ( Key >= 0 )
            {
              Key = StringCchCatW(v9, 0x56u, *v8);
              v3 = Key;
              if ( Key >= 0 )
                goto LABEL_36;
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_36;
              }
              v5 = 18;
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_36;
              }
              v5 = 17;
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_36;
            }
            v5 = 16;
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_36;
          v5 = 15;
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v5 = 14;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v5 = 13;
    }
    v6 = (unsigned int)Key;
    goto LABEL_35;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 12;
    v6 = v3;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, v6);
  }
LABEL_36:
  FwRegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x18005856c  push    rbx
0x18005856e  push    rbp
0x18005856f  push    rsi
0x180058570  push    rdi
0x180058571  push    r14
0x180058573  push    r15
0x180058575  sub     rsp, 38h
0x180058579  mov     rax, cs:__security_cookie
0x180058580  xor     rax, rsp
0x180058583  mov     [rsp+68h+var_40], rax
0x180058588  mov     rdi, rcx
0x18005858b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058592  lea     rbp, WPP_GLOBAL_Control
0x180058599  lea     r15, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x1800585a0  cmp     rcx, rbp
0x1800585a3  jz      short loc_1800585BC
0x1800585a5  test    byte ptr [rcx+1Ch], 8
0x1800585a9  jz      short loc_1800585BC
0x1800585ab  mov     rcx, [rcx+10h]
0x1800585af  mov     edx, 0Bh
0x1800585b4  mov     r8, r15
0x1800585b7  call    WPP_SF_
0x1800585bc  lea     rdx, [rsp+68h+phkResult]; phkResult
0x1800585c1  mov     [rsp+68h+phkResult], 0
0x1800585ca  mov     ecx, 0F003Fh; samDesired
0x1800585cf  call    cs:__imp_RegOpenCurrentUser
0x1800585d5  mov     ebx, eax
0x1800585d7  test    eax, eax
0x1800585d9  jle     short loc_1800585E4
0x1800585db  movzx   ebx, ax
0x1800585de  or      ebx, 80070000h
0x1800585e4  test    ebx, ebx
0x1800585e6  jns     short loc_18005860F
0x1800585e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800585ef  cmp     rcx, rbp
0x1800585f2  jz      loc_180058771
0x1800585f8  test    byte ptr [rcx+1Ch], 1
0x1800585fc  jz      loc_180058771
0x180058602  mov     edx, 0Ch
0x180058607  mov     r9d, ebx
0x18005860a  jmp     loc_180058765
0x18005860f  mov     rcx, [rsp+68h+phkResult]
0x180058614  lea     r9, [rdi+10h]
0x180058618  mov     r8d, 0F003Fh
0x18005861e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Firewall"
0x180058625  call    cs:__imp_FwRegCreateKey
0x18005862b  mov     ebx, eax
0x18005862d  test    eax, eax
0x18005862f  jns     short loc_180058655
0x180058631  mov     rcx, cs:WPP_GLOBAL_Control
0x180058638  cmp     rcx, rbp
0x18005863b  jz      loc_180058771
0x180058641  test    byte ptr [rcx+1Ch], 1
0x180058645  jz      loc_180058771
0x18005864b  mov     edx, 0Dh
0x180058650  jmp     loc_180058762
0x180058655  lea     rsi, [rdi+18h]
0x180058659  mov     rcx, rsi; unsigned __int16 **
0x18005865c  call    ?FwCreateGuidString@@YAJPEAPEAG@Z; FwCreateGuidString(ushort * *)
0x180058661  mov     ebx, eax
0x180058663  test    eax, eax
0x180058665  jns     short loc_18005868B
0x180058667  mov     rcx, cs:WPP_GLOBAL_Control
0x18005866e  cmp     rcx, rbp
0x180058671  jz      loc_180058771
0x180058677  test    byte ptr [rcx+1Ch], 1
0x18005867b  jz      loc_180058771
0x180058681  mov     edx, 0Eh
0x180058686  jmp     loc_180058762
0x18005868b  mov     rdx, [rsi]
0x18005868e  lea     r9, [rdi+8]
0x180058692  mov     rcx, [rdi+10h]
0x180058696  mov     r8d, 0F003Fh
0x18005869c  call    cs:__imp_FwRegCreateKey
0x1800586a2  mov     ebx, eax
0x1800586a4  test    eax, eax
0x1800586a6  jns     short loc_1800586CC
0x1800586a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586af  cmp     rcx, rbp
0x1800586b2  jz      loc_180058771
0x1800586b8  test    byte ptr [rcx+1Ch], 1
0x1800586bc  jz      loc_180058771
0x1800586c2  mov     edx, 0Fh
0x1800586c7  jmp     loc_180058762
0x1800586cc  add     rdi, 20h ; ' '
0x1800586d0  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows Firewall"
0x1800586d7  mov     r14d, 56h ; 'V'
0x1800586dd  mov     rcx, rdi; unsigned __int16 *
0x1800586e0  mov     edx, r14d; unsigned __int64
0x1800586e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800586e8  mov     ebx, eax
0x1800586ea  test    eax, eax
0x1800586ec  jns     short loc_180058706
0x1800586ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800586f5  cmp     rcx, rbp
0x1800586f8  jz      short loc_180058771
0x1800586fa  test    byte ptr [rcx+1Ch], 1
0x1800586fe  jz      short loc_180058771
0x180058700  lea     edx, [r14-46h]
0x180058704  jmp     short loc_180058762
0x180058706  lea     r8, asc_18007CAA4; "\\"
0x18005870d  mov     rdx, r14; unsigned __int64
0x180058710  mov     rcx, rdi; unsigned __int16 *
0x180058713  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058718  mov     ebx, eax
0x18005871a  test    eax, eax
0x18005871c  jns     short loc_180058737
0x18005871e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058725  cmp     rcx, rbp
0x180058728  jz      short loc_180058771
0x18005872a  test    byte ptr [rcx+1Ch], 1
0x18005872e  jz      short loc_180058771
0x180058730  mov     edx, 11h
0x180058735  jmp     short loc_180058762
0x180058737  mov     r8, [rsi]; unsigned __int16 *
0x18005873a  mov     rdx, r14; unsigned __int64
0x18005873d  mov     rcx, rdi; unsigned __int16 *
0x180058740  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058745  mov     ebx, eax
0x180058747  test    eax, eax
0x180058749  jns     short loc_180058771
0x18005874b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058752  cmp     rcx, rbp
0x180058755  jz      short loc_180058771
0x180058757  test    byte ptr [rcx+1Ch], 1
0x18005875b  jz      short loc_180058771
0x18005875d  mov     edx, 12h
0x180058762  mov     r9d, eax
0x180058765  mov     rcx, [rcx+10h]
0x180058769  mov     r8, r15
0x18005876c  call    WPP_SF_d
0x180058771  mov     rcx, [rsp+68h+phkResult]
0x180058776  call    cs:__imp_FwRegCloseKey
0x18005877c  mov     eax, ebx
0x18005877e  mov     rcx, [rsp+68h+var_40]
0x180058783  xor     rcx, rsp; StackCookie
0x180058786  call    __security_check_cookie
0x18005878b  add     rsp, 38h
0x18005878f  pop     r15
0x180058791  pop     r14
0x180058793  pop     rdi
0x180058794  pop     rsi
0x180058795  pop     rbp
0x180058796  pop     rbx
0x180058797  retn
```
