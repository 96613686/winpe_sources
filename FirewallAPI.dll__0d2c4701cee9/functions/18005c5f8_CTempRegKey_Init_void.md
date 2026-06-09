# CTempRegKey::Init(void)

- ea: `0x18005c5f8`
- end: `0x18005c83d`
- name: `?Init@CTempRegKey@@QEAAJXZ`
- size: `581`
- prototype: `__int64 __fastcall(CTempRegKey *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027370`
- `0x18005c844`

## callees

- `0x180005e0c`
- `0x1800185ec`
- `0x180025344`
- `0x1800294b0`
- `0x18003336c`
- `0x18005c4bc`
- `0x18005c5f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005c65b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005c65b`
- `fwbase!FwRegCreateKey` at `0x18005c6b7`
- `fwbase!FwRegCreateKey` at `0x18005c734`
- `fwbase!FwRegCreateKey` at `0x18005c6b7`
- `fwbase!FwRegCreateKey` at `0x18005c734`
- `fwbase!FwRegCloseKey` at `0x18005c814`
- `fwbase!FwRegCloseKey` at `0x18005c814`

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
0x18005c5f8  push    rbx
0x18005c5fa  push    rbp
0x18005c5fb  push    rsi
0x18005c5fc  push    rdi
0x18005c5fd  push    r14
0x18005c5ff  push    r15
0x18005c601  sub     rsp, 38h
0x18005c605  mov     rax, cs:__security_cookie
0x18005c60c  xor     rax, rsp
0x18005c60f  mov     [rsp+68h+var_40], rax
0x18005c614  mov     rdi, rcx
0x18005c617  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c61e  lea     rbp, WPP_GLOBAL_Control
0x18005c625  lea     r15, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18005c62c  cmp     rcx, rbp
0x18005c62f  jz      short loc_18005C648
0x18005c631  test    byte ptr [rcx+1Ch], 8
0x18005c635  jz      short loc_18005C648
0x18005c637  mov     rcx, [rcx+10h]
0x18005c63b  mov     edx, 0Bh
0x18005c640  mov     r8, r15
0x18005c643  call    WPP_SF_
0x18005c648  lea     rdx, [rsp+68h+phkResult]; phkResult
0x18005c64d  mov     [rsp+68h+phkResult], 0
0x18005c656  mov     ecx, 0F003Fh; samDesired
0x18005c65b  call    cs:__imp_RegOpenCurrentUser
0x18005c662  nop     dword ptr [rax+rax+00h]
0x18005c667  mov     ebx, eax
0x18005c669  test    eax, eax
0x18005c66b  jle     short loc_18005C676
0x18005c66d  movzx   ebx, ax
0x18005c670  or      ebx, 80070000h
0x18005c676  test    ebx, ebx
0x18005c678  jns     short loc_18005C6A1
0x18005c67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c681  cmp     rcx, rbp
0x18005c684  jz      loc_18005C80F
0x18005c68a  test    byte ptr [rcx+1Ch], 1
0x18005c68e  jz      loc_18005C80F
0x18005c694  mov     edx, 0Ch
0x18005c699  mov     r9d, ebx
0x18005c69c  jmp     loc_18005C803
0x18005c6a1  mov     rcx, [rsp+68h+phkResult]
0x18005c6a6  lea     r9, [rdi+10h]
0x18005c6aa  mov     r8d, 0F003Fh
0x18005c6b0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Firewall"
0x18005c6b7  call    cs:__imp_FwRegCreateKey
0x18005c6be  nop     dword ptr [rax+rax+00h]
0x18005c6c3  mov     ebx, eax
0x18005c6c5  test    eax, eax
0x18005c6c7  jns     short loc_18005C6ED
0x18005c6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c6d0  cmp     rcx, rbp
0x18005c6d3  jz      loc_18005C80F
0x18005c6d9  test    byte ptr [rcx+1Ch], 1
0x18005c6dd  jz      loc_18005C80F
0x18005c6e3  mov     edx, 0Dh
0x18005c6e8  jmp     loc_18005C800
0x18005c6ed  lea     rsi, [rdi+18h]
0x18005c6f1  mov     rcx, rsi; unsigned __int16 **
0x18005c6f4  call    ?FwCreateGuidString@@YAJPEAPEAG@Z; FwCreateGuidString(ushort * *)
0x18005c6f9  mov     ebx, eax
0x18005c6fb  test    eax, eax
0x18005c6fd  jns     short loc_18005C723
0x18005c6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c706  cmp     rcx, rbp
0x18005c709  jz      loc_18005C80F
0x18005c70f  test    byte ptr [rcx+1Ch], 1
0x18005c713  jz      loc_18005C80F
0x18005c719  mov     edx, 0Eh
0x18005c71e  jmp     loc_18005C800
0x18005c723  mov     rdx, [rsi]
0x18005c726  lea     r9, [rdi+8]
0x18005c72a  mov     rcx, [rdi+10h]
0x18005c72e  mov     r8d, 0F003Fh
0x18005c734  call    cs:__imp_FwRegCreateKey
0x18005c73b  nop     dword ptr [rax+rax+00h]
0x18005c740  mov     ebx, eax
0x18005c742  test    eax, eax
0x18005c744  jns     short loc_18005C76A
0x18005c746  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c74d  cmp     rcx, rbp
0x18005c750  jz      loc_18005C80F
0x18005c756  test    byte ptr [rcx+1Ch], 1
0x18005c75a  jz      loc_18005C80F
0x18005c760  mov     edx, 0Fh
0x18005c765  jmp     loc_18005C800
0x18005c76a  add     rdi, 20h ; ' '
0x18005c76e  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows Firewall"
0x18005c775  mov     r14d, 56h ; 'V'
0x18005c77b  mov     rcx, rdi; unsigned __int16 *
0x18005c77e  mov     edx, r14d; unsigned __int64
0x18005c781  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005c786  mov     ebx, eax
0x18005c788  test    eax, eax
0x18005c78a  jns     short loc_18005C7A4
0x18005c78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c793  cmp     rcx, rbp
0x18005c796  jz      short loc_18005C80F
0x18005c798  test    byte ptr [rcx+1Ch], 1
0x18005c79c  jz      short loc_18005C80F
0x18005c79e  lea     edx, [r14-46h]
0x18005c7a2  jmp     short loc_18005C800
0x18005c7a4  lea     r8, asc_180080AE4; "\\"
0x18005c7ab  mov     rdx, r14; unsigned __int64
0x18005c7ae  mov     rcx, rdi; unsigned __int16 *
0x18005c7b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c7b6  mov     ebx, eax
0x18005c7b8  test    eax, eax
0x18005c7ba  jns     short loc_18005C7D5
0x18005c7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7c3  cmp     rcx, rbp
0x18005c7c6  jz      short loc_18005C80F
0x18005c7c8  test    byte ptr [rcx+1Ch], 1
0x18005c7cc  jz      short loc_18005C80F
0x18005c7ce  mov     edx, 11h
0x18005c7d3  jmp     short loc_18005C800
0x18005c7d5  mov     r8, [rsi]; unsigned __int16 *
0x18005c7d8  mov     rdx, r14; unsigned __int64
0x18005c7db  mov     rcx, rdi; unsigned __int16 *
0x18005c7de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c7e3  mov     ebx, eax
0x18005c7e5  test    eax, eax
0x18005c7e7  jns     short loc_18005C80F
0x18005c7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7f0  cmp     rcx, rbp
0x18005c7f3  jz      short loc_18005C80F
0x18005c7f5  test    byte ptr [rcx+1Ch], 1
0x18005c7f9  jz      short loc_18005C80F
0x18005c7fb  mov     edx, 12h
0x18005c800  mov     r9d, eax
0x18005c803  mov     rcx, [rcx+10h]
0x18005c807  mov     r8, r15
0x18005c80a  call    WPP_SF_d
0x18005c80f  mov     rcx, [rsp+68h+phkResult]
0x18005c814  call    cs:__imp_FwRegCloseKey
0x18005c81b  nop     dword ptr [rax+rax+00h]
0x18005c820  mov     eax, ebx
0x18005c822  mov     rcx, [rsp+68h+var_40]
0x18005c827  xor     rcx, rsp; StackCookie
0x18005c82a  call    __security_check_cookie
0x18005c82f  add     rsp, 38h
0x18005c833  pop     r15
0x18005c835  pop     r14
0x18005c837  pop     rdi
0x18005c838  pop     rsi
0x18005c839  pop     rbp
0x18005c83a  pop     rbx
0x18005c83b  retn
```
