# ConstructSecurityDescriptorInternal(ulong,ulong,ulong,ulong,ulong,_SID * *,ulong *,ulong *,ulong,uchar *,ulong,ulong *)

- ea: `0x18001afec`
- end: `0x18001b36a`
- name: `?ConstructSecurityDescriptorInternal@@YAJKKKKKPEAPEAU_SID@@PEAK1KPEAEK1@Z`
- size: `894`
- prototype: `int(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, struct _SID **, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001c760`
- `0x1800df1c8`

## callees

- `0x180019ac4`
- `0x18001afec`
- `0x1800701d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001b0a6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001b0a6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001b029`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001b029`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b0c8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b0e9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b10a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b168`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b2fb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b319`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b337`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b355`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b0c8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b0e9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b10a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b168`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b2fb`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b319`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b337`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001b355`

## pseudocode

```c
__int64 __fastcall ConstructSecurityDescriptorInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        unsigned int a5,
        struct _SID **a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned int *a12)
{
  __int64 result; // rax
  DWORD v14; // eax
  DWORD v15; // edx
  DWORD v16; // ecx
  struct _ACL *v17; // rdi
  __int64 i; // rbx
  struct _SID *v19; // r9
  DWORD v20; // r8d

  a12 = 0;
  result = WxGetProcessUserSID((struct _SID **)&a12);
  if ( (int)result < 0 )
  {
    HIDWORD(a12) = 1240;
    return result;
  }
  v14 = GetLengthSid(a12) + 52;
  v15 = v14 + 96;
  if ( !a4 )
    v15 = v14;
  if ( a6 && a8 && *a6 && *a8 )
    v15 += *a7 + 8;
  v16 = v15 + 8;
  if ( !v15 )
    v16 = 0;
  if ( v16 + 20 > 0x190 )
  {
    result = 2147942487LL;
    HIDWORD(a12) = 1301;
    return result;
  }
  result = 0;
  *(_OWORD *)a10 = 0;
  *((_DWORD *)a10 + 4) = 0;
  *a10 = 1;
  *((_WORD *)a10 + 1) = 0x8000;
  if ( v16 )
  {
    *((_WORD *)a10 + 1) |= 4u;
    *((_DWORD *)a10 + 4) = 20;
    v17 = (struct _ACL *)(a10 + 20);
    if ( InitializeAcl((PACL)(a10 + 20), v16, 2u) )
    {
      if ( AddAccessAllowedAce(v17, 2u, 0x10000000u, a12) )
      {
        if ( AddAccessAllowedAce(v17, 2u, 0x10000000u, &c_rgbBuiltinAdministratorsSid) )
        {
          if ( AddAccessAllowedAce(v17, 2u, 0x10000000u, &c_rgbLocalSystemSid) )
          {
            result = 0;
            if ( !a4 )
            {
LABEL_14:
              if ( a6 && a8 )
              {
                for ( i = 0; !(_DWORD)i; i = 1 )
                {
                  v19 = a6[i];
                  if ( v19 )
                  {
                    v20 = a8[i];
                    if ( v20 )
                    {
                      if ( !AddAccessAllowedAce(v17, 2u, v20, v19) )
                      {
                        result = WxGetLastError();
                        if ( (int)result > 0 )
                          result = (unsigned __int16)result | 0x80070000;
                        HIDWORD(a12) = 1371;
                        goto LABEL_30;
                      }
                      result = 0;
                    }
                  }
                }
              }
              return result;
            }
            if ( AddAccessAllowedAce(v17, 2u, a4, &c_rgbBuiltinAnyPackageSid) )
            {
              if ( AddAccessAllowedAce(v17, 2u, a4, &c_rgbCapabilityInternetClientSid) )
              {
                if ( AddAccessAllowedAce(v17, 2u, a4, &c_rgbCapabilityInternetClientServerSid) )
                {
                  if ( AddAccessAllowedAce(v17, 2u, a4, &c_rgbCapabilityPrivateNetworkClientServerSid) )
                  {
                    result = 0;
                    goto LABEL_14;
                  }
                  result = WxGetLastError();
                  if ( (int)result > 0 )
                    result = (unsigned __int16)result | 0x80070000;
                  HIDWORD(a12) = 1360;
                }
                else
                {
                  result = WxGetLastError();
                  if ( (int)result > 0 )
                    result = (unsigned __int16)result | 0x80070000;
                  HIDWORD(a12) = 1359;
                }
              }
              else
              {
                result = WxGetLastError();
                if ( (int)result > 0 )
                  result = (unsigned __int16)result | 0x80070000;
                HIDWORD(a12) = 1358;
              }
            }
            else
            {
              result = WxGetLastError();
              if ( (int)result > 0 )
                result = (unsigned __int16)result | 0x80070000;
              HIDWORD(a12) = 1357;
            }
          }
          else
          {
            result = WxGetLastError();
            if ( (int)result > 0 )
              result = (unsigned __int16)result | 0x80070000;
            HIDWORD(a12) = 1352;
          }
        }
        else
        {
          result = WxGetLastError();
          if ( (int)result > 0 )
            result = (unsigned __int16)result | 0x80070000;
          HIDWORD(a12) = 1347;
        }
      }
      else
      {
        result = WxGetLastError();
        if ( (int)result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        HIDWORD(a12) = 1342;
      }
    }
    else
    {
      result = WxGetLastError();
      if ( (int)result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HIDWORD(a12) = 1338;
    }
LABEL_30:
    if ( (int)result >= 0 )
      return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001afec  mov     rax, rsp
0x18001afef  push    rbx
0x18001aff0  push    rsi
0x18001aff1  push    rdi
0x18001aff2  push    r14
0x18001aff4  push    r15
0x18001aff6  sub     rsp, 20h
0x18001affa  mov     [rsp+48h+arg_5C], 0
0x18001b005  lea     rcx, [rax+60h]; struct _SID **
0x18001b009  mov     qword ptr [rax+60h], 0
0x18001b011  mov     ebx, r9d
0x18001b014  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x18001b019  test    eax, eax
0x18001b01b  js      loc_18001B155
0x18001b021  mov     rcx, [rsp+0A8h]; pSid
0x18001b029  call    cs:__imp_GetLengthSid
0x18001b02f  mov     r14, [rsp+48h+arg_28]
0x18001b034  add     eax, 34h ; '4'
0x18001b037  mov     rsi, [rsp+48h+arg_38]
0x18001b03f  test    ebx, ebx
0x18001b041  lea     edx, [rax+60h]
0x18001b044  cmovz   edx, eax
0x18001b047  test    r14, r14
0x18001b04a  jnz     loc_18001B17A
0x18001b050  test    edx, edx
0x18001b052  lea     ecx, [rdx+8]
0x18001b055  cmovz   ecx, edx
0x18001b058  lea     eax, [rcx+14h]
0x18001b05b  cmp     eax, 190h
0x18001b060  ja      loc_18001B2D6
0x18001b066  mov     rdi, [rsp+48h+arg_48]
0x18001b06e  xor     eax, eax
0x18001b070  xorps   xmm0, xmm0
0x18001b073  movups  xmmword ptr [rdi], xmm0
0x18001b076  mov     [rdi+10h], eax
0x18001b079  mov     byte ptr [rdi], 1
0x18001b07c  mov     word ptr [rdi+2], 8000h
0x18001b082  test    ecx, ecx
0x18001b084  jz      loc_18001B127
0x18001b08a  or      word ptr [rdi+2], 4
0x18001b08f  lea     r15d, [rax+2]
0x18001b093  mov     dword ptr [rdi+10h], 14h
0x18001b09a  mov     edx, ecx; nAclLength
0x18001b09c  add     rdi, 14h
0x18001b0a0  mov     r8d, r15d; dwAclRevision
0x18001b0a3  mov     rcx, rdi; pAcl
0x18001b0a6  call    cs:__imp_InitializeAcl
0x18001b0ac  test    eax, eax
0x18001b0ae  jz      loc_18001B1C4
0x18001b0b4  mov     r9, [rsp+0A8h]; pSid
0x18001b0bc  mov     r8d, 10000000h; AccessMask
0x18001b0c2  mov     edx, r15d; dwAceRevision
0x18001b0c5  mov     rcx, rdi; pAcl
0x18001b0c8  call    cs:__imp_AddAccessAllowedAce
0x18001b0ce  test    eax, eax
0x18001b0d0  jz      loc_18001B1D7
0x18001b0d6  lea     r9, c_rgbBuiltinAdministratorsSid; pSid
0x18001b0dd  mov     r8d, 10000000h; AccessMask
0x18001b0e3  mov     edx, r15d; dwAceRevision
0x18001b0e6  mov     rcx, rdi; pAcl
0x18001b0e9  call    cs:__imp_AddAccessAllowedAce
0x18001b0ef  test    eax, eax
0x18001b0f1  jz      loc_18001B1F5
0x18001b0f7  lea     r9, c_rgbLocalSystemSid; pSid
0x18001b0fe  mov     r8d, 10000000h; AccessMask
0x18001b104  mov     edx, r15d; dwAceRevision
0x18001b107  mov     rcx, rdi; pAcl
0x18001b10a  call    cs:__imp_AddAccessAllowedAce
0x18001b110  test    eax, eax
0x18001b112  jz      loc_18001B213
0x18001b118  xor     eax, eax
0x18001b11a  test    ebx, ebx
0x18001b11c  jnz     loc_18001B2EB
0x18001b122  test    r14, r14
0x18001b125  jnz     short loc_18001B133
0x18001b127  add     rsp, 20h
0x18001b12b  pop     r15
0x18001b12d  pop     r14
0x18001b12f  pop     rdi
0x18001b130  pop     rsi
0x18001b131  pop     rbx
0x18001b132  retn
0x18001b133  test    rsi, rsi
0x18001b136  jz      short loc_18001B127
0x18001b138  xor     ebx, ebx
0x18001b13a  cmp     ebx, 1
0x18001b13d  jnb     short loc_18001B127
0x18001b13f  mov     r9, [r14+rbx*8]; pSid
0x18001b143  test    r9, r9
0x18001b146  jz      short loc_18001B151
0x18001b148  mov     r8d, [rsi+rbx*4]; AccessMask
0x18001b14c  test    r8d, r8d
0x18001b14f  jnz     short loc_18001B162
0x18001b151  inc     ebx
0x18001b153  jmp     short loc_18001B13A
0x18001b155  mov     [rsp+48h+arg_5C], 4D8h
0x18001b160  jmp     short loc_18001B127
0x18001b162  mov     edx, r15d; dwAceRevision
0x18001b165  mov     rcx, rdi; pAcl
0x18001b168  call    cs:__imp_AddAccessAllowedAce
0x18001b16e  test    eax, eax
0x18001b170  jz      loc_18001B2B5
0x18001b176  xor     eax, eax
0x18001b178  jmp     short loc_18001B151
0x18001b17a  test    rsi, rsi
0x18001b17d  jz      loc_18001B050
0x18001b183  cmp     qword ptr [r14], 0
0x18001b187  jz      loc_18001B050
0x18001b18d  cmp     dword ptr [rsi], 0
0x18001b190  jz      loc_18001B050
0x18001b196  mov     rax, [rsp+48h+arg_30]
0x18001b19e  mov     ecx, [rax]
0x18001b1a0  add     ecx, 8
0x18001b1a3  add     edx, ecx
0x18001b1a5  jmp     loc_18001B050
0x18001b1aa  mov     [rsp+48h+arg_5C], 53Ah
0x18001b1b5  test    eax, eax
0x18001b1b7  mov     ecx, 8000FFFFh
0x18001b1bc  cmovns  eax, ecx
0x18001b1bf  jmp     loc_18001B127
0x18001b1c4  call    WxGetLastError
0x18001b1c9  test    eax, eax
0x18001b1cb  jle     short loc_18001B1AA
0x18001b1cd  movzx   eax, ax
0x18001b1d0  or      eax, 80070000h
0x18001b1d5  jmp     short loc_18001B1AA
0x18001b1d7  call    WxGetLastError
0x18001b1dc  test    eax, eax
0x18001b1de  jle     short loc_18001B1E8
0x18001b1e0  movzx   eax, ax
0x18001b1e3  or      eax, 80070000h
0x18001b1e8  mov     [rsp+48h+arg_5C], 53Eh
0x18001b1f3  jmp     short loc_18001B1B5
0x18001b1f5  call    WxGetLastError
0x18001b1fa  test    eax, eax
0x18001b1fc  jle     short loc_18001B206
0x18001b1fe  movzx   eax, ax
0x18001b201  or      eax, 80070000h
0x18001b206  mov     [rsp+48h+arg_5C], 543h
0x18001b211  jmp     short loc_18001B1B5
0x18001b213  call    WxGetLastError
0x18001b218  test    eax, eax
0x18001b21a  jle     short loc_18001B224
0x18001b21c  movzx   eax, ax
0x18001b21f  or      eax, 80070000h
0x18001b224  mov     [rsp+48h+arg_5C], 548h
0x18001b22f  jmp     short loc_18001B1B5
0x18001b231  call    WxGetLastError
0x18001b236  test    eax, eax
0x18001b238  jle     short loc_18001B242
0x18001b23a  movzx   eax, ax
0x18001b23d  or      eax, 80070000h
0x18001b242  mov     [rsp+48h+arg_5C], 54Dh
0x18001b24d  jmp     loc_18001B1B5
0x18001b252  call    WxGetLastError
0x18001b257  test    eax, eax
0x18001b259  jle     short loc_18001B263
0x18001b25b  movzx   eax, ax
0x18001b25e  or      eax, 80070000h
0x18001b263  mov     [rsp+48h+arg_5C], 54Eh
0x18001b26e  jmp     loc_18001B1B5
0x18001b273  call    WxGetLastError
0x18001b278  test    eax, eax
0x18001b27a  jle     short loc_18001B284
0x18001b27c  movzx   eax, ax
0x18001b27f  or      eax, 80070000h
0x18001b284  mov     [rsp+48h+arg_5C], 54Fh
0x18001b28f  jmp     loc_18001B1B5
0x18001b294  call    WxGetLastError
0x18001b299  test    eax, eax
0x18001b29b  jle     short loc_18001B2A5
0x18001b29d  movzx   eax, ax
0x18001b2a0  or      eax, 80070000h
0x18001b2a5  mov     [rsp+48h+arg_5C], 550h
0x18001b2b0  jmp     loc_18001B1B5
0x18001b2b5  call    WxGetLastError
0x18001b2ba  test    eax, eax
0x18001b2bc  jle     short loc_18001B2C6
0x18001b2be  movzx   eax, ax
0x18001b2c1  or      eax, 80070000h
0x18001b2c6  mov     [rsp+48h+arg_5C], 55Bh
0x18001b2d1  jmp     loc_18001B1B5
0x18001b2d6  mov     eax, 80070057h
0x18001b2db  mov     [rsp+48h+arg_5C], 515h
0x18001b2e6  jmp     loc_18001B127
0x18001b2eb  lea     r9, c_rgbBuiltinAnyPackageSid; pSid
0x18001b2f2  mov     r8d, ebx; AccessMask
0x18001b2f5  mov     edx, r15d; dwAceRevision
0x18001b2f8  mov     rcx, rdi; pAcl
0x18001b2fb  call    cs:__imp_AddAccessAllowedAce
0x18001b301  test    eax, eax
0x18001b303  jz      loc_18001B231
0x18001b309  lea     r9, c_rgbCapabilityInternetClientSid; pSid
0x18001b310  mov     r8d, ebx; AccessMask
0x18001b313  mov     edx, r15d; dwAceRevision
0x18001b316  mov     rcx, rdi; pAcl
0x18001b319  call    cs:__imp_AddAccessAllowedAce
0x18001b31f  test    eax, eax
0x18001b321  jz      loc_18001B252
0x18001b327  lea     r9, c_rgbCapabilityInternetClientServerSid; pSid
0x18001b32e  mov     r8d, ebx; AccessMask
0x18001b331  mov     edx, r15d; dwAceRevision
0x18001b334  mov     rcx, rdi; pAcl
0x18001b337  call    cs:__imp_AddAccessAllowedAce
0x18001b33d  test    eax, eax
0x18001b33f  jz      loc_18001B273
0x18001b345  lea     r9, c_rgbCapabilityPrivateNetworkClientServerSid; pSid
0x18001b34c  mov     r8d, ebx; AccessMask
0x18001b34f  mov     edx, r15d; dwAceRevision
0x18001b352  mov     rcx, rdi; pAcl
0x18001b355  call    cs:__imp_AddAccessAllowedAce
0x18001b35b  test    eax, eax
0x18001b35d  jz      loc_18001B294
0x18001b363  xor     eax, eax
0x18001b365  jmp     loc_18001B122
```
