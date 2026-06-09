# ScHelperCMSVerifyMessage(uchar *,ulong,int,char *,uchar * *,ulong *,_CERT_CONTEXT const * *,_CRYPT_ALGORITHM_IDENTIFIER * *)

- ea: `0x18006dcd8`
- end: `0x18006df4d`
- name: `?ScHelperCMSVerifyMessage@@YAHPEAEKHPEADPEAPEAEPEAKPEAPEBU_CERT_CONTEXT@@PEAPEAU_CRYPT_ALGORITHM_IDENTIFIER@@@Z`
- size: `629`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, DWORD cbData@<edx>, int@<r8d>, char *@<r9>, unsigned __int8 **, unsigned int *, const struct _CERT_CONTEXT **, struct _CRYPT_ALGORITHM_IDENTIFIER **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18006e5d8`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18006d8c0`
- `0x18006dcd8`
- `0x18006df54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006deeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006deeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006dee5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006df10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006dee5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006df10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006de7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006de7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006df1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006df1e`
- `CRYPT32!CryptMsgGetParam` at `0x18006ddb2`
- `CRYPT32!CryptMsgGetParam` at `0x18006de0f`
- `CRYPT32!CryptMsgGetParam` at `0x18006de6b`
- `CRYPT32!CryptMsgGetParam` at `0x18006dea2`
- `CRYPT32!CryptMsgGetParam` at `0x18006ddb2`
- `CRYPT32!CryptMsgGetParam` at `0x18006de0f`
- `CRYPT32!CryptMsgGetParam` at `0x18006de6b`
- `CRYPT32!CryptMsgGetParam` at `0x18006dea2`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18006dd5e`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18006dd5e`
- `CRYPT32!CryptMsgUpdate` at `0x18006dd81`
- `CRYPT32!CryptMsgUpdate` at `0x18006dd81`
- `CRYPT32!CryptMsgClose` at `0x18006defe`
- `CRYPT32!CryptMsgClose` at `0x18006defe`

## pseudocode

```c
__int64 __fastcall ScHelperCMSVerifyMessage(
        BYTE *pbData,
        DWORD cbData,
        __int64 a3,
        char *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        struct _CERT_CONTEXT **a7,
        struct _CRYPT_ALGORITHM_IDENTIFIER **a8)
{
  unsigned __int8 *v11; // rdi
  HCRYPTMSG v12; // rax
  void *v13; // rbx
  unsigned int v14; // esi
  unsigned int v15; // ecx
  unsigned int v16; // r8d
  struct _CRYPT_ALGORITHM_IDENTIFIER *Param; // rax
  DWORD LastError; // r14d
  unsigned int *v19; // rcx
  DWORD pcbData; // [rsp+30h] [rbp-B9h] BYREF
  DWORD v22; // [rsp+34h] [rbp-B5h] BYREF
  int pvData; // [rsp+38h] [rbp-B1h] BYREF
  struct _CERT_CONTEXT **v24; // [rsp+40h] [rbp-A9h]
  unsigned __int8 **v25; // [rsp+48h] [rbp-A1h]
  unsigned int *v26; // [rsp+50h] [rbp-99h]
  char v27[128]; // [rsp+60h] [rbp-89h] BYREF

  *a5 = 0;
  v25 = a5;
  v11 = 0;
  *a6 = 0;
  v26 = a6;
  v24 = a7;
  pvData = 0;
  pcbData = 0;
  v22 = 0;
  if ( a8 )
    *a8 = 0;
  v12 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v13 = v12;
  if ( v12 )
  {
    v14 = 1;
    if ( CryptMsgUpdate(v12, pbData, cbData, 1) )
    {
      pcbData = 4;
      pvData = 0;
      if ( CryptMsgGetParam(v13, 1u, 0, &pvData, &pcbData) )
      {
        if ( pcbData != 4 || pvData != 2 )
          goto LABEL_18;
        if ( !a4 )
          goto LABEL_28;
        memset_0(v27, 0, sizeof(v27));
        pcbData = 128;
        if ( !CryptMsgGetParam(v13, 4u, 0, v27, &pcbData) )
          goto LABEL_19;
        v15 = strcmp(v27, a4);
        if ( v15 )
        {
LABEL_18:
          SetLastError(8u);
        }
        else
        {
LABEL_28:
          if ( ScHelperGetSignerCertAndVerify(v15, v13, (const struct _CERT_CONTEXT **)v24) )
          {
            if ( CryptMsgGetParam(v13, 2u, 0, 0, &v22) )
            {
              v11 = (unsigned __int8 *)LocalAlloc(0x40u, v22);
              if ( v11 )
              {
                if ( CryptMsgGetParam(v13, 2u, 0, v11, &v22) )
                {
                  if ( !a8
                    || (Param = (struct _CRYPT_ALGORITHM_IDENTIFIER *)ScHelperAllocAndMsgGetParam(v13, 8u, v16),
                        (*a8 = Param) != 0) )
                  {
                    LastError = 0;
                    v19 = v26;
                    *v25 = v11;
                    v11 = 0;
                    *v19 = v22;
                    goto LABEL_20;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_19:
  v14 = 0;
  LastError = GetLastError();
  if ( v13 )
  {
LABEL_20:
    CryptMsgClose(v13);
    if ( v14 )
      goto LABEL_23;
  }
  if ( LastError )
    SetLastError(LastError);
LABEL_23:
  if ( v11 )
    LocalFree(v11);
  return v14;
}

```

## disassembly

```asm
0x18006dcd8  mov     [rsp-8+arg_10], rbx
0x18006dcdd  push    rbp
0x18006dcde  push    rsi
0x18006dcdf  push    rdi
0x18006dce0  push    r12
0x18006dce2  push    r13
0x18006dce4  push    r14
0x18006dce6  push    r15
0x18006dce8  lea     rbp, [rsp-7]
0x18006dced  sub     rsp, 0F0h
0x18006dcf4  mov     rax, cs:__security_cookie
0x18006dcfb  xor     rax, rsp
0x18006dcfe  mov     [rbp+37h+var_40], rax
0x18006dd02  mov     rax, [rbp+37h+arg_20]
0x18006dd06  xor     esi, esi
0x18006dd08  mov     r15, [rbp+37h+arg_38]
0x18006dd0c  mov     r12, rcx
0x18006dd0f  mov     rcx, [rbp+37h+arg_28]
0x18006dd13  mov     r13d, edx
0x18006dd16  mov     rdx, [rbp+37h+arg_30]
0x18006dd1a  mov     r14, r9
0x18006dd1d  mov     [rax], rsi
0x18006dd20  mov     r8d, esi; dwMsgType
0x18006dd23  mov     [rsp+120h+var_D8], rax
0x18006dd28  mov     edi, esi
0x18006dd2a  mov     [rcx], esi
0x18006dd2c  mov     [rsp+120h+var_D0], rcx
0x18006dd31  mov     [rsp+120h+var_E0], rdx
0x18006dd36  mov     [rsp+120h+pvData], esi
0x18006dd3a  mov     [rsp+120h+pcbData], esi
0x18006dd3e  mov     [rsp+120h+var_EC], esi
0x18006dd42  test    r15, r15
0x18006dd45  jz      short loc_18006DD4A
0x18006dd47  mov     [r15], rsi
0x18006dd4a  mov     [rsp+120h+pStreamInfo], rsi; pStreamInfo
0x18006dd4f  xor     r9d, r9d; hCryptProv
0x18006dd52  xor     edx, edx; dwFlags
0x18006dd54  mov     [rsp+120h+pRecipientInfo], rsi; pRecipientInfo
0x18006dd59  mov     ecx, 10001h; dwMsgEncodingType
0x18006dd5e  call    cs:__imp_CryptMsgOpenToDecode
0x18006dd64  mov     rbx, rax
0x18006dd67  test    rax, rax
0x18006dd6a  jz      loc_18006DEEB
0x18006dd70  mov     esi, 1
0x18006dd75  mov     r8d, r13d; cbData
0x18006dd78  mov     r9d, esi; fFinal
0x18006dd7b  mov     rdx, r12; pbData
0x18006dd7e  mov     rcx, rax; hCryptMsg
0x18006dd81  call    cs:__imp_CryptMsgUpdate
0x18006dd87  test    eax, eax
0x18006dd89  jz      loc_18006DEEB
0x18006dd8f  lea     rax, [rsp+120h+pcbData]
0x18006dd94  mov     [rsp+120h+pcbData], 4
0x18006dd9c  lea     r9, [rsp+120h+pvData]; pvData
0x18006dda1  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x18006dda6  xor     r8d, r8d; dwIndex
0x18006dda9  mov     [rsp+120h+pvData], edi
0x18006ddad  mov     edx, esi; dwParamType
0x18006ddaf  mov     rcx, rbx; hCryptMsg
0x18006ddb2  call    cs:__imp_CryptMsgGetParam
0x18006ddb8  test    eax, eax
0x18006ddba  jz      loc_18006DEEB
0x18006ddc0  cmp     [rsp+120h+pcbData], 4
0x18006ddc5  jnz     loc_18006DEE0
0x18006ddcb  lea     r13d, [rsi+1]
0x18006ddcf  cmp     [rsp+120h+pvData], r13d
0x18006ddd4  jnz     loc_18006DEE0
0x18006ddda  test    r14, r14
0x18006dddd  jz      short loc_18006DE40
0x18006dddf  lea     r12d, [rsi+7Fh]
0x18006dde3  xor     edx, edx; Val
0x18006dde5  mov     r8d, r12d; Size
0x18006dde8  lea     rcx, [rsp+120h+var_C0]; void *
0x18006dded  call    memset_0
0x18006ddf2  lea     rax, [rsp+120h+pcbData]
0x18006ddf7  mov     [rsp+120h+pcbData], r12d
0x18006ddfc  lea     r9, [rsp+120h+var_C0]; pvData
0x18006de01  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x18006de06  xor     r8d, r8d; dwIndex
0x18006de09  lea     edx, [rsi+3]; dwParamType
0x18006de0c  mov     rcx, rbx; hCryptMsg
0x18006de0f  call    cs:__imp_CryptMsgGetParam
0x18006de15  test    eax, eax
0x18006de17  jz      loc_18006DEEB
0x18006de1d  lea     rax, [rsp+120h+var_C0]
0x18006de22  sub     r14, rax
0x18006de25  movzx   ecx, byte ptr [rax]
0x18006de28  movzx   edx, byte ptr [rax+r14]
0x18006de2d  sub     ecx, edx; unsigned int
0x18006de2f  jnz     short loc_18006DE38
0x18006de31  add     rax, rsi
0x18006de34  test    edx, edx
0x18006de36  jnz     short loc_18006DE25
0x18006de38  test    ecx, ecx
0x18006de3a  jnz     loc_18006DEE0
0x18006de40  mov     r8, [rsp+120h+var_E0]; struct _CERT_CONTEXT **
0x18006de45  mov     rdx, rbx; void *
0x18006de48  call    ?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z; ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)
0x18006de4d  test    eax, eax
0x18006de4f  jz      loc_18006DEEB
0x18006de55  lea     rax, [rsp+120h+var_EC]
0x18006de5a  xor     r9d, r9d; pvData
0x18006de5d  xor     r8d, r8d; dwIndex
0x18006de60  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x18006de65  mov     edx, r13d; dwParamType
0x18006de68  mov     rcx, rbx; hCryptMsg
0x18006de6b  call    cs:__imp_CryptMsgGetParam
0x18006de71  test    eax, eax
0x18006de73  jz      short loc_18006DEEB
0x18006de75  mov     edx, [rsp+120h+var_EC]; uBytes
0x18006de79  mov     ecx, 40h ; '@'; uFlags
0x18006de7e  call    cs:__imp_LocalAlloc
0x18006de84  mov     rdi, rax
0x18006de87  test    rax, rax
0x18006de8a  jz      short loc_18006DEEB
0x18006de8c  lea     rax, [rsp+120h+var_EC]
0x18006de91  mov     r9, rdi; pvData
0x18006de94  xor     r8d, r8d; dwIndex
0x18006de97  mov     [rsp+120h+pRecipientInfo], rax; pcbData
0x18006de9c  mov     edx, r13d; dwParamType
0x18006de9f  mov     rcx, rbx; hCryptMsg
0x18006dea2  call    cs:__imp_CryptMsgGetParam
0x18006dea8  test    eax, eax
0x18006deaa  jz      short loc_18006DEEB
0x18006deac  test    r15, r15
0x18006deaf  jz      short loc_18006DEC6
0x18006deb1  mov     edx, 8; dwParamType
0x18006deb6  mov     rcx, rbx; hCryptMsg
0x18006deb9  call    ?ScHelperAllocAndMsgGetParam@@YAPEAXPEAXKK@Z; ScHelperAllocAndMsgGetParam(void *,ulong,ulong)
0x18006debe  mov     [r15], rax
0x18006dec1  test    rax, rax
0x18006dec4  jz      short loc_18006DEEB
0x18006dec6  mov     rax, [rsp+120h+var_D8]
0x18006decb  xor     r14d, r14d
0x18006dece  mov     rcx, [rsp+120h+var_D0]
0x18006ded3  mov     [rax], rdi
0x18006ded6  xor     edi, edi
0x18006ded8  mov     eax, [rsp+120h+var_EC]
0x18006dedc  mov     [rcx], eax
0x18006dede  jmp     short loc_18006DEFB
0x18006dee0  mov     ecx, 8; dwErrCode
0x18006dee5  call    cs:__imp_SetLastError
0x18006deeb  call    cs:__imp_GetLastError
0x18006def1  xor     esi, esi
0x18006def3  mov     r14d, eax
0x18006def6  test    rbx, rbx
0x18006def9  jz      short loc_18006DF08
0x18006defb  mov     rcx, rbx; hCryptMsg
0x18006defe  call    cs:__imp_CryptMsgClose
0x18006df04  test    esi, esi
0x18006df06  jnz     short loc_18006DF16
0x18006df08  test    r14d, r14d
0x18006df0b  jz      short loc_18006DF16
0x18006df0d  mov     ecx, r14d; dwErrCode
0x18006df10  call    cs:__imp_SetLastError
0x18006df16  test    rdi, rdi
0x18006df19  jz      short loc_18006DF24
0x18006df1b  mov     rcx, rdi; hMem
0x18006df1e  call    cs:__imp_LocalFree
0x18006df24  mov     eax, esi
0x18006df26  mov     rcx, [rbp+37h+var_40]
0x18006df2a  xor     rcx, rsp; StackCookie
0x18006df2d  call    __security_check_cookie
0x18006df32  mov     rbx, [rsp+120h+arg_10]
0x18006df3a  add     rsp, 0F0h
0x18006df41  pop     r15
0x18006df43  pop     r14
0x18006df45  pop     r13
0x18006df47  pop     r12
0x18006df49  pop     rdi
0x18006df4a  pop     rsi
0x18006df4b  pop     rbp
0x18006df4c  retn
```
