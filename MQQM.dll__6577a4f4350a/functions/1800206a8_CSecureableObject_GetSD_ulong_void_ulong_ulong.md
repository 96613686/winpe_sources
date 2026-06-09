# CSecureableObject::GetSD(ulong,void *,ulong,ulong *)

- ea: `0x1800206a8`
- end: `0x180020875`
- name: `?GetSD@CSecureableObject@@QEAAJKPEAXKPEAK@Z`
- size: `461`
- prototype: `int(CSecureableObject *__hidden this, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c64c`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x1800205c8`
- `0x1800206a8`
- `0x18002c61c`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x180020715`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180020715`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800207ea`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800207ea`
- `KERNEL32!GetLastError` at `0x18002071f`
- `KERNEL32!GetLastError` at `0x1800207f4`
- `KERNEL32!GetLastError` at `0x18002071f`
- `KERNEL32!GetLastError` at `0x1800207f4`
- `mqsec!MQSec_CopySecurityDescriptor` at `0x180020789`
- `mqsec!MQSec_CopySecurityDescriptor` at `0x180020789`

## pseudocode

```c
__int64 __fastcall CSecureableObject::GetSD(
        CSecureableObject *this,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        unsigned int *lpdwBufferLength)
{
  __int64 result; // rax
  signed int LastError; // ebx
  unsigned __int16 v11; // r8
  bool v12; // sf
  bool v13; // sf
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]

  result = *((unsigned int *)this + 5);
  if ( (int)result >= 0 )
  {
    LastError = CSecureableObject::AccessCheck(this, ((a2 & 8) << 21) | 0x20000);
    if ( LastError < 0 )
    {
      v11 = 10;
      goto LABEL_4;
    }
    v15 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          10,
          WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids,
          (unsigned int)LastError);
      v12 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v12 = LastError < 0;
      }
      if ( !v12 )
        return (unsigned int)LastError;
      v11 = 1100;
LABEL_4:
      LogMsgHR(LastError, (wchar_t *)L"csecobj", v11);
      return (unsigned int)LastError;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(_OWORD *, _QWORD, _QWORD, _QWORD))MQSec_CopySecurityDescriptor)(
                          pSecurityDescriptor,
                          *((_QWORD *)this + 1),
                          a2,
                          0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids);
      v11 = 1102;
      LastError = -1072824287;
      goto LABEL_4;
    }
    *lpdwBufferLength = a4;
    if ( !MakeSelfRelativeSD(pSecurityDescriptor, a3, lpdwBufferLength) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          12,
          WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids,
          (unsigned int)LastError);
      if ( LastError == 122 )
      {
        v11 = 1104;
        LastError = -1072824285;
      }
      else
      {
        v13 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v13 = LastError < 0;
        }
        if ( !v13 )
          return (unsigned int)LastError;
        v11 = 1105;
      }
      goto LABEL_4;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800206a8  push    rbx
0x1800206aa  push    rbp
0x1800206ab  push    rsi
0x1800206ac  push    rdi
0x1800206ad  push    r14
0x1800206af  sub     rsp, 50h
0x1800206b3  mov     eax, [rcx+14h]
0x1800206b6  mov     ebp, r9d
0x1800206b9  mov     r14, r8
0x1800206bc  mov     esi, edx
0x1800206be  mov     rdi, rcx
0x1800206c1  test    eax, eax
0x1800206c3  js      loc_18002086A
0x1800206c9  and     edx, 8
0x1800206cc  shl     edx, 15h
0x1800206cf  bts     edx, 11h; unsigned int
0x1800206d3  call    ?AccessCheck@CSecureableObject@@QEAAJK@Z; CSecureableObject::AccessCheck(ulong)
0x1800206d8  mov     ebx, eax
0x1800206da  test    eax, eax
0x1800206dc  jns     short loc_1800206F9
0x1800206de  mov     r8d, 0Ah; unsigned __int16
0x1800206e4  lea     rdx, aCsecobj; "csecobj"
0x1800206eb  mov     ecx, ebx; int
0x1800206ed  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800206f2  mov     eax, ebx
0x1800206f4  jmp     loc_18002086A
0x1800206f9  xor     eax, eax
0x1800206fb  lea     rcx, [rsp+78h+pSecurityDescriptor]; pSecurityDescriptor
0x180020700  xorps   xmm0, xmm0
0x180020703  mov     [rsp+78h+var_38], rax
0x180020708  movups  [rsp+78h+pSecurityDescriptor], xmm0
0x18002070d  lea     edx, [rax+1]; dwRevision
0x180020710  movups  [rsp+78h+var_48], xmm0
0x180020715  call    cs:__imp_InitializeSecurityDescriptor
0x18002071b  test    eax, eax
0x18002071d  jnz     short loc_18002077A
0x18002071f  call    cs:__imp_GetLastError
0x180020725  mov     ebx, eax
0x180020727  mov     rcx, cs:WPP_GLOBAL_Control
0x18002072e  lea     rax, WPP_GLOBAL_Control
0x180020735  cmp     rcx, rax
0x180020738  jz      short loc_18002075E
0x18002073a  test    byte ptr [rcx+10Ch], 1
0x180020741  jz      short loc_18002075E
0x180020743  mov     rcx, [rcx+100h]
0x18002074a  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020751  mov     edx, 0Ah
0x180020756  mov     r9d, ebx
0x180020759  call    WPP_SF_d
0x18002075e  test    ebx, ebx
0x180020760  jle     short loc_18002076D
0x180020762  movzx   ebx, bx
0x180020765  or      ebx, 80070000h
0x18002076b  test    ebx, ebx
0x18002076d  jns     short loc_1800206F2
0x18002076f  mov     r8d, 44Ch
0x180020775  jmp     loc_1800206E4
0x18002077a  mov     rdx, [rdi+8]
0x18002077e  lea     rcx, [rsp+78h+pSecurityDescriptor]
0x180020783  xor     r9d, r9d
0x180020786  mov     r8d, esi
0x180020789  call    cs:__imp_?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z; MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)
0x18002078f  test    eax, eax
0x180020791  jnz     short loc_1800207D7
0x180020793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002079a  lea     rax, WPP_GLOBAL_Control
0x1800207a1  cmp     rcx, rax
0x1800207a4  jz      short loc_1800207C7
0x1800207a6  test    byte ptr [rcx+10Ch], 1
0x1800207ad  jz      short loc_1800207C7
0x1800207af  mov     rcx, [rcx+100h]
0x1800207b6  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x1800207bd  mov     edx, 0Bh
0x1800207c2  call    WPP_SF_
0x1800207c7  mov     r8d, 44Eh
0x1800207cd  mov     ebx, 0C00E0021h
0x1800207d2  jmp     loc_1800206E4
0x1800207d7  mov     r8, [rsp+78h+lpdwBufferLength]; lpdwBufferLength
0x1800207df  lea     rcx, [rsp+78h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800207e4  mov     rdx, r14; pSelfRelativeSecurityDescriptor
0x1800207e7  mov     [r8], ebp
0x1800207ea  call    cs:__imp_MakeSelfRelativeSD
0x1800207f0  test    eax, eax
0x1800207f2  jnz     short loc_180020868
0x1800207f4  call    cs:__imp_GetLastError
0x1800207fa  mov     ebx, eax
0x1800207fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020803  lea     rax, WPP_GLOBAL_Control
0x18002080a  cmp     rcx, rax
0x18002080d  jz      short loc_180020833
0x18002080f  test    byte ptr [rcx+10Ch], 1
0x180020816  jz      short loc_180020833
0x180020818  mov     rcx, [rcx+100h]
0x18002081f  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020826  mov     edx, 0Ch
0x18002082b  mov     r9d, ebx
0x18002082e  call    WPP_SF_d
0x180020833  cmp     ebx, 7Ah ; 'z'
0x180020836  jnz     short loc_180020848
0x180020838  mov     r8d, 450h
0x18002083e  mov     ebx, 0C00E0023h
0x180020843  jmp     loc_1800206E4
0x180020848  test    ebx, ebx
0x18002084a  jle     short loc_180020857
0x18002084c  movzx   ebx, bx
0x18002084f  or      ebx, 80070000h
0x180020855  test    ebx, ebx
0x180020857  jns     loc_1800206F2
0x18002085d  mov     r8d, 451h
0x180020863  jmp     loc_1800206E4
0x180020868  xor     eax, eax
0x18002086a  add     rsp, 50h
0x18002086e  pop     r14
0x180020870  pop     rdi
0x180020871  pop     rsi
0x180020872  pop     rbp
0x180020873  pop     rbx
0x180020874  retn
```
