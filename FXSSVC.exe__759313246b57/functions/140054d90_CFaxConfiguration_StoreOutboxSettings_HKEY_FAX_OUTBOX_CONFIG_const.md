# CFaxConfiguration::StoreOutboxSettings(HKEY__ *,_FAX_OUTBOX_CONFIG * const)

- ea: `0x140054d90`
- end: `0x140055089`
- name: `?StoreOutboxSettings@CFaxConfiguration@@AEBAKPEAUHKEY__@@QEAU_FAX_OUTBOX_CONFIG@@@Z`
- size: `761`
- prototype: `unsigned int __fastcall(CFaxConfiguration *__hidden this, HKEY, struct _FAX_OUTBOX_CONFIG *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140054800`
- `0x1400555f8`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140054d90`
- `0x140075070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140054df0`
- `KERNEL32!GetLastError` at `0x140054e43`
- `KERNEL32!GetLastError` at `0x140054e96`
- `KERNEL32!GetLastError` at `0x140054ee9`
- `KERNEL32!GetLastError` at `0x140054f3c`
- `KERNEL32!GetLastError` at `0x140054f8f`
- `KERNEL32!GetLastError` at `0x140054fee`
- `KERNEL32!GetLastError` at `0x140055040`
- `KERNEL32!GetLastError` at `0x140054df0`
- `KERNEL32!GetLastError` at `0x140054e43`
- `KERNEL32!GetLastError` at `0x140054e96`
- `KERNEL32!GetLastError` at `0x140054ee9`
- `KERNEL32!GetLastError` at `0x140054f3c`
- `KERNEL32!GetLastError` at `0x140054f8f`
- `KERNEL32!GetLastError` at `0x140054fee`
- `KERNEL32!GetLastError` at `0x140055040`

## string_xrefs

- `0x140054f29`: `UseDeviceTsid`

## pseudocode

```c
__int64 __fastcall CFaxConfiguration::StoreOutboxSettings(
        CFaxConfiguration *this,
        HKEY a2,
        struct _FAX_OUTBOX_CONFIG *const a3)
{
  DWORD LastError; // eax
  DWORD v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
  }
  if ( (unsigned int)SetRegistryDword(a2, L"Retries", *((_DWORD *)a3 + 3)) )
  {
    if ( (unsigned int)SetRegistryDword(a2, L"Retry Delay", *((_DWORD *)a3 + 4)) )
    {
      if ( (unsigned int)SetRegistryDword(a2, L"QueueAgeLimit", *((_DWORD *)a3 + 7)) )
      {
        if ( (unsigned int)SetRegistryDword(a2, L"Branding", *((_DWORD *)a3 + 8)) )
        {
          if ( (unsigned int)SetRegistryDword(a2, L"UseDeviceTsid", *((_DWORD *)a3 + 2)) )
          {
            if ( (unsigned int)SetRegistryDword(a2, L"AllowPersonalCoverPages", *((_DWORD *)a3 + 1)) )
            {
              if ( (unsigned int)SetRegistryDword(a2, L"StartCheapTime", *((_DWORD *)a3 + 5)) )
              {
                v6 = 0;
                if ( !(unsigned int)SetRegistryDword(a2, L"StopCheapTime", *((_DWORD *)a3 + 6)) )
                {
                  LastError = GetLastError();
                  v6 = LastError;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v8 = 47;
                    goto LABEL_45;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v6 = LastError;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v8 = 46;
                  goto LABEL_45;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v8 = 45;
                goto LABEL_45;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 44;
              goto LABEL_45;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v6 = LastError;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 43;
            goto LABEL_45;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 42;
          goto LABEL_45;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 41;
        goto LABEL_45;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 40;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, LastError);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140054d90  push    rbx
0x140054d92  push    rsi
0x140054d93  push    rdi
0x140054d94  push    r14
0x140054d96  push    r15
0x140054d98  sub     rsp, 20h
0x140054d9c  mov     rdi, r8
0x140054d9f  mov     rsi, rdx
0x140054da2  mov     rcx, cs:WPP_GLOBAL_Control
0x140054da9  lea     r14, WPP_GLOBAL_Control
0x140054db0  lea     r15, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x140054db7  cmp     rcx, r14
0x140054dba  jz      short loc_140054DD9
0x140054dbc  test    byte ptr [rcx+1Ch], 4
0x140054dc0  jz      short loc_140054DD9
0x140054dc2  cmp     byte ptr [rcx+19h], 5
0x140054dc6  jb      short loc_140054DD9
0x140054dc8  mov     rcx, [rcx+10h]
0x140054dcc  mov     edx, 27h ; '''
0x140054dd1  mov     r8, r15
0x140054dd4  call    WPP_SF_
0x140054dd9  mov     r8d, [rdi+0Ch]
0x140054ddd  lea     rdx, aRetries; "Retries"
0x140054de4  mov     rcx, rsi
0x140054de7  call    SetRegistryDword
0x140054dec  test    eax, eax
0x140054dee  jnz     short loc_140054E2C
0x140054df0  call    cs:__imp_GetLastError
0x140054df7  nop     dword ptr [rax+rax+00h]
0x140054dfc  mov     ebx, eax
0x140054dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140054e05  cmp     rcx, r14
0x140054e08  jz      loc_14005507A
0x140054e0e  test    byte ptr [rcx+1Ch], 4
0x140054e12  jz      loc_14005507A
0x140054e18  cmp     byte ptr [rcx+19h], 2
0x140054e1c  jb      loc_14005507A
0x140054e22  mov     edx, 28h ; '('
0x140054e27  jmp     loc_14005506B
0x140054e2c  mov     r8d, [rdi+10h]
0x140054e30  lea     rdx, aRetryDelay; "Retry Delay"
0x140054e37  mov     rcx, rsi
0x140054e3a  call    SetRegistryDword
0x140054e3f  test    eax, eax
0x140054e41  jnz     short loc_140054E7F
0x140054e43  call    cs:__imp_GetLastError
0x140054e4a  nop     dword ptr [rax+rax+00h]
0x140054e4f  mov     ebx, eax
0x140054e51  mov     rcx, cs:WPP_GLOBAL_Control
0x140054e58  cmp     rcx, r14
0x140054e5b  jz      loc_14005507A
0x140054e61  test    byte ptr [rcx+1Ch], 4
0x140054e65  jz      loc_14005507A
0x140054e6b  cmp     byte ptr [rcx+19h], 2
0x140054e6f  jb      loc_14005507A
0x140054e75  mov     edx, 29h ; ')'
0x140054e7a  jmp     loc_14005506B
0x140054e7f  mov     r8d, [rdi+1Ch]
0x140054e83  lea     rdx, aQueueagelimit; "QueueAgeLimit"
0x140054e8a  mov     rcx, rsi
0x140054e8d  call    SetRegistryDword
0x140054e92  test    eax, eax
0x140054e94  jnz     short loc_140054ED2
0x140054e96  call    cs:__imp_GetLastError
0x140054e9d  nop     dword ptr [rax+rax+00h]
0x140054ea2  mov     ebx, eax
0x140054ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140054eab  cmp     rcx, r14
0x140054eae  jz      loc_14005507A
0x140054eb4  test    byte ptr [rcx+1Ch], 4
0x140054eb8  jz      loc_14005507A
0x140054ebe  cmp     byte ptr [rcx+19h], 2
0x140054ec2  jb      loc_14005507A
0x140054ec8  mov     edx, 2Ah ; '*'
0x140054ecd  jmp     loc_14005506B
0x140054ed2  mov     r8d, [rdi+20h]
0x140054ed6  lea     rdx, aBranding; "Branding"
0x140054edd  mov     rcx, rsi
0x140054ee0  call    SetRegistryDword
0x140054ee5  test    eax, eax
0x140054ee7  jnz     short loc_140054F25
0x140054ee9  call    cs:__imp_GetLastError
0x140054ef0  nop     dword ptr [rax+rax+00h]
0x140054ef5  mov     ebx, eax
0x140054ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140054efe  cmp     rcx, r14
0x140054f01  jz      loc_14005507A
0x140054f07  test    byte ptr [rcx+1Ch], 4
0x140054f0b  jz      loc_14005507A
0x140054f11  cmp     byte ptr [rcx+19h], 2
0x140054f15  jb      loc_14005507A
0x140054f1b  mov     edx, 2Bh ; '+'
0x140054f20  jmp     loc_14005506B
0x140054f25  mov     r8d, [rdi+8]
0x140054f29  lea     rdx, aUsedevicetsid; "UseDeviceTsid"
0x140054f30  mov     rcx, rsi
0x140054f33  call    SetRegistryDword
0x140054f38  test    eax, eax
0x140054f3a  jnz     short loc_140054F78
0x140054f3c  call    cs:__imp_GetLastError
0x140054f43  nop     dword ptr [rax+rax+00h]
0x140054f48  mov     ebx, eax
0x140054f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054f51  cmp     rcx, r14
0x140054f54  jz      loc_14005507A
0x140054f5a  test    byte ptr [rcx+1Ch], 4
0x140054f5e  jz      loc_14005507A
0x140054f64  cmp     byte ptr [rcx+19h], 2
0x140054f68  jb      loc_14005507A
0x140054f6e  mov     edx, 2Ch ; ','
0x140054f73  jmp     loc_14005506B
0x140054f78  mov     r8d, [rdi+4]
0x140054f7c  lea     rdx, aAllowpersonalc; "AllowPersonalCoverPages"
0x140054f83  mov     rcx, rsi
0x140054f86  call    SetRegistryDword
0x140054f8b  test    eax, eax
0x140054f8d  jnz     short loc_140054FCB
0x140054f8f  call    cs:__imp_GetLastError
0x140054f96  nop     dword ptr [rax+rax+00h]
0x140054f9b  mov     ebx, eax
0x140054f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054fa4  cmp     rcx, r14
0x140054fa7  jz      loc_14005507A
0x140054fad  test    byte ptr [rcx+1Ch], 4
0x140054fb1  jz      loc_14005507A
0x140054fb7  cmp     byte ptr [rcx+19h], 2
0x140054fbb  jb      loc_14005507A
0x140054fc1  mov     edx, 2Dh ; '-'
0x140054fc6  jmp     loc_14005506B
0x140054fcb  movzx   r8d, word ptr [rdi+16h]
0x140054fd0  lea     rdx, aStartcheaptime; "StartCheapTime"
0x140054fd7  movzx   eax, word ptr [rdi+14h]
0x140054fdb  mov     rcx, rsi
0x140054fde  shl     r8d, 10h
0x140054fe2  or      r8d, eax
0x140054fe5  call    SetRegistryDword
0x140054fea  test    eax, eax
0x140054fec  jnz     short loc_14005501B
0x140054fee  call    cs:__imp_GetLastError
0x140054ff5  nop     dword ptr [rax+rax+00h]
0x140054ffa  mov     ebx, eax
0x140054ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x140055003  cmp     rcx, r14
0x140055006  jz      short loc_14005507A
0x140055008  test    byte ptr [rcx+1Ch], 4
0x14005500c  jz      short loc_14005507A
0x14005500e  cmp     byte ptr [rcx+19h], 2
0x140055012  jb      short loc_14005507A
0x140055014  mov     edx, 2Eh ; '.'
0x140055019  jmp     short loc_14005506B
0x14005501b  movzx   r8d, word ptr [rdi+1Ah]
0x140055020  lea     rdx, aStopcheaptime; "StopCheapTime"
0x140055027  movzx   eax, word ptr [rdi+18h]
0x14005502b  mov     rcx, rsi
0x14005502e  shl     r8d, 10h
0x140055032  xor     ebx, ebx
0x140055034  or      r8d, eax
0x140055037  call    SetRegistryDword
0x14005503c  test    eax, eax
0x14005503e  jnz     short loc_14005507A
0x140055040  call    cs:__imp_GetLastError
0x140055047  nop     dword ptr [rax+rax+00h]
0x14005504c  mov     ebx, eax
0x14005504e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055055  cmp     rcx, r14
0x140055058  jz      short loc_14005507A
0x14005505a  test    byte ptr [rcx+1Ch], 4
0x14005505e  jz      short loc_14005507A
0x140055060  cmp     byte ptr [rcx+19h], 2
0x140055064  jb      short loc_14005507A
0x140055066  mov     edx, 2Fh ; '/'
0x14005506b  mov     rcx, [rcx+10h]
0x14005506f  mov     r9d, eax
0x140055072  mov     r8, r15
0x140055075  call    WPP_SF_d
0x14005507a  mov     eax, ebx
0x14005507c  add     rsp, 20h
0x140055080  pop     r15
0x140055082  pop     r14
0x140055084  pop     rdi
0x140055085  pop     rsi
0x140055086  pop     rbx
0x140055087  retn
```
