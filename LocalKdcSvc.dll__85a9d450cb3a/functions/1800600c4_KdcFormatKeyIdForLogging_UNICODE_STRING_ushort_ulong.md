# KdcFormatKeyIdForLogging(_UNICODE_STRING *,ushort *,ulong)

- ea: `0x1800600c4`
- end: `0x180060447`
- name: `?KdcFormatKeyIdForLogging@@YAXPEAU_UNICODE_STRING@@PEAGK@Z`
- size: `899`
- prototype: `void __fastcall(struct _UNICODE_STRING *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060c24`

## callees

- `0x180002ad0`
- `0x180003980`
- `0x180004d34`
- `0x1800053d4`
- `0x1800101c4`
- `0x1800101ec`
- `0x180033fac`
- `0x1800342fc`
- `0x18005a060`
- `0x18005a090`
- `0x18005bbdc`
- `0x18005bc30`
- `0x18005bc50`
- `0x1800600c4`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800601cb`
- `bcrypt!BCryptGetProperty` at `0x1800601cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006016d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006016d`
- `bcrypt!BCryptFinishHash` at `0x180060345`
- `bcrypt!BCryptFinishHash` at `0x180060345`
- `bcrypt!BCryptDestroyHash` at `0x180060276`
- `bcrypt!BCryptDestroyHash` at `0x180060276`
- `bcrypt!BCryptHashData` at `0x1800602fe`
- `bcrypt!BCryptHashData` at `0x1800602fe`
- `bcrypt!BCryptCreateHash` at `0x1800602b4`
- `bcrypt!BCryptCreateHash` at `0x1800602b4`

## pseudocode

```c
void __fastcall KdcFormatKeyIdForLogging(struct _UNICODE_STRING *a1, unsigned __int16 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  CSecurityData *v7; // rcx
  __int64 v8; // rdx
  UCHAR *v9; // rbx
  BCRYPT_HASH_HANDLE v10; // rdi
  ULONG v11; // esi
  size_t v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  CSecurityData *v15; // rcx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  unsigned int v18; // edi
  char v19; // [rsp+40h] [rbp-79h] BYREF
  NTSTATUS Property; // [rsp+44h] [rbp-75h] BYREF
  size_t BufferCount; // [rsp+48h] [rbp-71h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-69h] BYREF
  UCHAR pbOutput[4]; // [rsp+58h] [rbp-61h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp-59h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-49h] BYREF
  ULONG pcbResult; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v27[8]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v28[40]; // [rsp+88h] [rbp-31h] BYREF
  char v29; // [rsp+B0h] [rbp-9h] BYREF
  UCHAR v30[16]; // [rsp+D0h] [rbp+17h] BYREF
  __int128 v31; // [rsp+E0h] [rbp+27h]

  Buffer = a2;
  LODWORD(BufferCount) = 261;
  Property = 0;
  phAlgorithm = 0;
  hHash = 0;
  *(_DWORD *)pbOutput = 0;
  *(_OWORD *)v30 = 0;
  pcbResult = 0;
  v31 = 0;
  v19 = 1;
  v3 = lambda_e2fdf73ad8eb742709e641475192cf4b_::_lambda_e2fdf73ad8eb742709e641475192cf4b_(
         (unsigned int)&v29,
         (unsigned int)&Property,
         (unsigned int)&v19,
         (unsigned int)&Buffer,
         (__int64)&BufferCount);
  wil::scope_exit__lambda_e2fdf73ad8eb742709e641475192cf4b___(v28, v3);
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  v6 = (unsigned int)Property;
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    v6 = (unsigned int)Property;
    if ( Property < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v8 = 104;
      goto LABEL_9;
    }
    v9 = (UCHAR *)MIDL_user_allocate(*(unsigned int *)pbOutput);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
      goto LABEL_14;
    }
    v10 = hHash;
    v11 = *(_DWORD *)pbOutput;
    if ( hHash )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v27);
      BCryptDestroyHash(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v27);
    }
    hHash = 0;
    Property = BCryptCreateHash(phAlgorithm, &hHash, v9, v11, 0, 0, 0);
    v14 = (unsigned int)Property;
    if ( Property >= 0 )
    {
      Property = BCryptHashData(hHash, (PUCHAR)a1->Buffer, a1->Length, 0);
      v14 = (unsigned int)Property;
      if ( Property >= 0 )
      {
        Property = BCryptFinishHash(hHash, v30, 0x20u, 0);
        v14 = (unsigned int)Property;
        if ( Property >= 0 )
        {
          v12 = (unsigned int)BufferCount;
          if ( (unsigned int)BufferCount <= 0x40 )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
            }
          }
          else
          {
            v17 = Buffer;
            v18 = 0;
            do
            {
              swprintf_s(v17, v12, L"%02X", v30[v18++]);
              v17 = Buffer + 2;
              v12 = (unsigned int)(BufferCount - 2);
              Buffer += 2;
              LODWORD(BufferCount) = BufferCount - 2;
            }
            while ( v18 < 0x20 );
            v19 = 0;
          }
          goto LABEL_37;
        }
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_37:
          wil::details::lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___::_lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___(
            v28,
            v12,
            v13,
            v14);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
          MIDL_user_free(v9);
          goto LABEL_38;
        }
        v16 = 108;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_37;
        }
        v16 = 107;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v16 = 106;
    }
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v14);
    goto LABEL_37;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_14;
  v8 = 103;
LABEL_9:
  WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v6);
LABEL_14:
  wil::details::lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___::_lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___(
    v28,
    v4,
    v5,
    v6);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
LABEL_38:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
}

```

## disassembly

```asm
0x1800600c4  mov     [rsp-8+arg_10], rbx
0x1800600c9  mov     [rsp-8+arg_18], rsi
0x1800600ce  push    rbp
0x1800600cf  push    rdi
0x1800600d0  push    r14
0x1800600d2  lea     rbp, [rsp-47h]
0x1800600d7  sub     rsp, 100h
0x1800600de  mov     rax, cs:__security_cookie
0x1800600e5  xor     rax, rsp
0x1800600e8  mov     [rbp+57h+var_20], rax
0x1800600ec  mov     [rbp+57h+Buffer], rdx
0x1800600f0  lea     rax, [rbp+57h+BufferCount]
0x1800600f4  xorps   xmm0, xmm0
0x1800600f7  mov     [rsp+110h+pcbResult], rax
0x1800600fc  mov     r14, rcx
0x1800600ff  mov     dword ptr [rbp+57h+BufferCount], 105h
0x180060106  lea     rdx, [rbp+57h+var_CC]
0x18006010a  mov     [rbp+57h+var_CC], 0
0x180060111  lea     rcx, [rbp+57h+var_60]
0x180060115  mov     [rbp+57h+phAlgorithm], 0
0x18006011d  lea     r9, [rbp+57h+Buffer]
0x180060121  mov     [rbp+57h+hHash], 0
0x180060129  lea     r8, [rbp+57h+var_D0]
0x18006012d  mov     dword ptr [rbp+57h+pbOutput], 0
0x180060134  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180060138  mov     [rbp+57h+var_98], 0
0x18006013f  movups  [rbp+57h+var_30], xmm0
0x180060143  mov     [rbp+57h+var_D0], 1
0x180060147  call    _lambda_e2fdf73ad8eb742709e641475192cf4b____lambda_e2fdf73ad8eb742709e641475192cf4b_
0x18006014c  mov     rdx, rax
0x18006014f  lea     rcx, [rbp+57h+var_88]
0x180060153  call    wil__scope_exit__lambda_e2fdf73ad8eb742709e641475192cf4b___
0x180060158  xor     r9d, r9d; dwFlags
0x18006015b  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180060162  lea     rdx, pszAlgId; "SHA256"
0x180060169  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18006016d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180060173  mov     [rbp+57h+var_CC], eax
0x180060176  mov     r9d, eax
0x180060179  test    eax, eax
0x18006017b  jns     short loc_1800601A5
0x18006017d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060184  lea     rax, WPP_GLOBAL_Control
0x18006018b  cmp     rcx, rax
0x18006018e  jz      loc_180060247
0x180060194  test    byte ptr [rcx+1Ch], 1
0x180060198  jz      loc_180060247
0x18006019e  mov     edx, 67h ; 'g'
0x1800601a3  jmp     short loc_1800601F9
0x1800601a5  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800601a9  lea     rax, [rbp+57h+var_98]
0x1800601ad  mov     [rsp+110h+dwFlags], 0; dwFlags
0x1800601b5  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800601b9  mov     r9d, 4; cbOutput
0x1800601bf  mov     [rsp+110h+pcbResult], rax; pcbResult
0x1800601c4  lea     rdx, pszProperty; "ObjectLength"
0x1800601cb  call    cs:__imp_BCryptGetProperty
0x1800601d1  mov     [rbp+57h+var_CC], eax
0x1800601d4  mov     r9d, eax
0x1800601d7  test    eax, eax
0x1800601d9  jns     short loc_18006020B
0x1800601db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800601e2  lea     rax, WPP_GLOBAL_Control
0x1800601e9  cmp     rcx, rax
0x1800601ec  jz      short loc_180060247
0x1800601ee  test    byte ptr [rcx+1Ch], 1
0x1800601f2  jz      short loc_180060247
0x1800601f4  mov     edx, 68h ; 'h'
0x1800601f9  mov     rcx, [rcx+10h]
0x1800601fd  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060204  call    WPP_SF_d
0x180060209  jmp     short loc_180060247
0x18006020b  mov     ecx, dword ptr [rbp+57h+pbOutput]; size
0x18006020e  call    MIDL_user_allocate
0x180060213  mov     rbx, rax
0x180060216  test    rax, rax
0x180060219  jnz     short loc_18006025E
0x18006021b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060222  lea     rax, WPP_GLOBAL_Control
0x180060229  cmp     rcx, rax
0x18006022c  jz      short loc_180060247
0x18006022e  test    byte ptr [rcx+1Ch], 1
0x180060232  jz      short loc_180060247
0x180060234  mov     rcx, [rcx+10h]
0x180060238  lea     edx, [rbx+69h]
0x18006023b  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060242  call    WPP_SF_
0x180060247  lea     rcx, [rbp+57h+var_88]
0x18006024b  call    wil__details__lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b______lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___
0x180060250  lea     rcx, [rbp+57h+hHash]
0x180060254  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180060259  jmp     loc_18006041A
0x18006025e  mov     rdi, [rbp+57h+hHash]
0x180060262  mov     esi, dword ptr [rbp+57h+pbOutput]
0x180060265  test    rdi, rdi
0x180060268  jz      short loc_180060285
0x18006026a  lea     rcx, [rbp+57h+var_90]; this
0x18006026e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180060273  mov     rcx, rdi; hHash
0x180060276  call    cs:__imp_BCryptDestroyHash
0x18006027c  lea     rcx, [rbp+57h+var_90]; this
0x180060280  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180060285  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180060289  lea     rdx, [rbp+57h+hHash]; phHash
0x18006028d  mov     [rsp+110h+var_E0], 0; dwFlags
0x180060295  mov     r9d, esi; cbHashObject
0x180060298  mov     [rsp+110h+dwFlags], 0; cbSecret
0x1800602a0  mov     r8, rbx; pbHashObject
0x1800602a3  mov     [rsp+110h+pcbResult], 0; pbSecret
0x1800602ac  mov     [rbp+57h+hHash], 0
0x1800602b4  call    cs:__imp_BCryptCreateHash
0x1800602ba  mov     [rbp+57h+var_CC], eax
0x1800602bd  mov     r9d, eax
0x1800602c0  test    eax, eax
0x1800602c2  jns     short loc_1800602EF
0x1800602c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800602cb  lea     rax, WPP_GLOBAL_Control
0x1800602d2  cmp     rcx, rax
0x1800602d5  jz      loc_180060400
0x1800602db  test    byte ptr [rcx+1Ch], 1
0x1800602df  jz      loc_180060400
0x1800602e5  mov     edx, 6Ah ; 'j'
0x1800602ea  jmp     loc_18006037B
0x1800602ef  movzx   r8d, word ptr [r14]; cbInput
0x1800602f3  xor     r9d, r9d; dwFlags
0x1800602f6  mov     rdx, [r14+8]; pbInput
0x1800602fa  mov     rcx, [rbp+57h+hHash]; hHash
0x1800602fe  call    cs:__imp_BCryptHashData
0x180060304  mov     [rbp+57h+var_CC], eax
0x180060307  mov     r9d, eax
0x18006030a  test    eax, eax
0x18006030c  jns     short loc_180060336
0x18006030e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060315  lea     rax, WPP_GLOBAL_Control
0x18006031c  cmp     rcx, rax
0x18006031f  jz      loc_180060400
0x180060325  test    byte ptr [rcx+1Ch], 1
0x180060329  jz      loc_180060400
0x18006032f  mov     edx, 6Bh ; 'k'
0x180060334  jmp     short loc_18006037B
0x180060336  mov     rcx, [rbp+57h+hHash]; hHash
0x18006033a  lea     rdx, [rbp+57h+var_40]; pbOutput
0x18006033e  xor     r9d, r9d; dwFlags
0x180060341  lea     r8d, [r9+20h]; cbOutput
0x180060345  call    cs:__imp_BCryptFinishHash
0x18006034b  mov     [rbp+57h+var_CC], eax
0x18006034e  mov     r9d, eax
0x180060351  test    eax, eax
0x180060353  jns     short loc_18006038D
0x180060355  mov     rcx, cs:WPP_GLOBAL_Control
0x18006035c  lea     rax, WPP_GLOBAL_Control
0x180060363  cmp     rcx, rax
0x180060366  jz      loc_180060400
0x18006036c  test    byte ptr [rcx+1Ch], 1
0x180060370  jz      loc_180060400
0x180060376  mov     edx, 6Ch ; 'l'
0x18006037b  mov     rcx, [rcx+10h]
0x18006037f  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060386  call    WPP_SF_d
0x18006038b  jmp     short loc_180060400
0x18006038d  mov     edx, dword ptr [rbp+57h+BufferCount]; BufferCount
0x180060390  cmp     edx, 40h ; '@'
0x180060393  jbe     short loc_1800603D2
0x180060395  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180060399  xor     edi, edi
0x18006039b  movsxd  rax, edi
0x18006039e  lea     r8, a02x; "%02X"
0x1800603a5  movzx   r9d, [rbp+rax+57h+var_40]
0x1800603ab  call    swprintf_s
0x1800603b0  mov     rcx, [rbp+57h+Buffer]
0x1800603b4  inc     edi
0x1800603b6  mov     edx, dword ptr [rbp+57h+BufferCount]
0x1800603b9  add     rcx, 4
0x1800603bd  add     edx, 0FFFFFFFEh
0x1800603c0  mov     [rbp+57h+Buffer], rcx
0x1800603c4  mov     dword ptr [rbp+57h+BufferCount], edx
0x1800603c7  cmp     edi, 20h ; ' '
0x1800603ca  jb      short loc_18006039B
0x1800603cc  mov     [rbp+57h+var_D0], 0
0x1800603d0  jmp     short loc_180060400
0x1800603d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800603d9  lea     rax, WPP_GLOBAL_Control
0x1800603e0  cmp     rcx, rax
0x1800603e3  jz      short loc_180060400
0x1800603e5  test    byte ptr [rcx+1Ch], 1
0x1800603e9  jz      short loc_180060400
0x1800603eb  mov     rcx, [rcx+10h]
0x1800603ef  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x1800603f6  mov     edx, 6Dh ; 'm'
0x1800603fb  call    WPP_SF_
0x180060400  lea     rcx, [rbp+57h+var_88]
0x180060404  call    wil__details__lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b______lambda_call__lambda_e2fdf73ad8eb742709e641475192cf4b___
0x180060409  lea     rcx, [rbp+57h+hHash]
0x18006040d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180060412  mov     rcx, rbx; void *
0x180060415  call    MIDL_user_free
0x18006041a  lea     rcx, [rbp+57h+phAlgorithm]
0x18006041e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180060423  mov     rcx, [rbp+57h+var_20]
0x180060427  xor     rcx, rsp; StackCookie
0x18006042a  call    __security_check_cookie
0x18006042f  lea     r11, [rsp+110h+var_10]
0x180060437  mov     rbx, [r11+30h]
0x18006043b  mov     rsi, [r11+38h]
0x18006043f  mov     rsp, r11
0x180060442  pop     r14
0x180060444  pop     rdi
0x180060445  pop     rbp
0x180060446  retn
```
