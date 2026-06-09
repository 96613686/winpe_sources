# Windows::Networking::UX::Internal::Profile::GetEAPMethodName(ushort * *)

- ea: `0x18007502c`
- end: `0x18007527b`
- name: `?GetEAPMethodName@Profile@Internal@UX@Networking@Windows@@QEAAJPEAPEAG@Z`
- size: `591`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::Profile *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005c450`

## callees

- `0x180009d4c`
- `0x18000de4c`
- `0x18001d4d4`
- `0x180074dc4`
- `0x180074e44`
- `0x18007502c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800751bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800751bf`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075237`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075237`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800750b0`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800750b0`
- `wlanapi!WpFreeProfile` at `0x180075207`
- `wlanapi!WpFreeProfile` at `0x180075207`
- `wlanapi!WpParseProfileXml` at `0x1800750e4`
- `wlanapi!WpParseProfileXml` at `0x1800750e4`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180075224`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180075224`
- `eappcfg!EapHostPeerGetMethods` at `0x18007514e`
- `eappcfg!EapHostPeerGetMethods` at `0x18007514e`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::Profile::GetEAPMethodName(
        Windows::Networking::UX::Internal::Profile *this,
        unsigned __int16 **a2)
{
  void *v4; // rcx
  signed int Profile; // eax
  signed int Methods; // ebx
  int v7; // eax
  EAP_ERROR *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // rdx
  DWORD v13; // ecx
  EAP_METHOD_INFO *pEapMethods; // rdi
  __int64 v15; // rbx
  LPWSTR pwszFriendlyName; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rsi
  unsigned __int16 *v19; // rax
  EAP_ERROR *pEapError; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR pstrProfileXml; // [rsp+48h] [rbp-38h] BYREF
  EAP_METHOD_INFO_ARRAY pEapMethodInfoArray; // [rsp+50h] [rbp-30h] BYREF
  EAP_ERROR **p_pEapError; // [rsp+60h] [rbp-20h] BYREF
  EAP_ERROR *ppEapError; // [rsp+68h] [rbp-18h] BYREF
  char v26; // [rsp+70h] [rbp-10h]
  DWORD pdwGrantedAccess; // [rsp+C0h] [rbp+40h] BYREF
  DWORD pdwFlags; // [rsp+C8h] [rbp+48h] BYREF
  int v29; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v30; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_660af29b5b58392da31645ec246aada0_Traceguids);
  *a2 = 0;
  v4 = *(void **)this;
  pstrProfileXml = 0;
  pdwFlags = 0;
  pdwGrantedAccess = 0;
  Profile = WlanGetProfile(
              v4,
              (const GUID *)((char *)this + 8),
              (LPCWSTR)this + 12,
              0,
              &pstrProfileXml,
              &pdwFlags,
              &pdwGrantedAccess);
  Methods = Profile;
  if ( Profile > 0 )
    Methods = (unsigned __int16)Profile | 0x80070000;
  if ( Methods >= 0 )
  {
    v30 = 0;
    v29 = 0;
    v7 = WpParseProfileXml(pstrProfileXml, &v30, 0, &v29);
    Methods = v7;
    if ( v7 > 0 )
      Methods = (unsigned __int16)v7 | 0x80070000;
    if ( Methods >= 0 )
    {
      pEapMethodInfoArray = 0;
      v8 = 0;
      pEapError = 0;
      v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 552) + 32LL) + 424LL);
      if ( *(_DWORD *)(v9 + 32) )
      {
        v10 = *(_QWORD *)(v9 + 48);
        p_pEapError = &pEapError;
        ppEapError = 0;
        v26 = 1;
        v11 = *(_DWORD *)(v10 + 64);
        Methods = EapHostPeerGetMethods(&pEapMethodInfoArray, &ppEapError);
        wil::details::out_param_t<wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&void EapHostPeerFreeErrorMemory(_EAP_ERROR *)>>>::~out_param_t<wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&void EapHostPeerFreeErrorMemory(_EAP_ERROR *)>>>(&p_pEapError);
        if ( Methods )
        {
          if ( Methods > 0 )
            Methods = (unsigned __int16)Methods | 0x80070000;
        }
        else
        {
          v12 = v11;
          v13 = 0;
          pEapMethods = pEapMethodInfoArray.pEapMethods;
          while ( 1 )
          {
            if ( v13 >= pEapMethodInfoArray.dwNumberOfMethods )
            {
              Methods = -2147024894;
              goto LABEL_27;
            }
            v15 = v13;
            if ( pEapMethodInfoArray.pEapMethods[v13].eaptype.eapType.type == *(_BYTE *)(v12 + v10 + 4)
              && pEapMethodInfoArray.pEapMethods[v13].eaptype.eapType.dwVendorId == *(_DWORD *)(v12 + v10 + 8)
              && pEapMethodInfoArray.pEapMethods[v13].eaptype.dwAuthorId == *(_DWORD *)(v12 + v10 + 16) )
            {
              break;
            }
            ++v13;
          }
          pwszFriendlyName = pEapMethodInfoArray.pEapMethods[v13].pwszFriendlyName;
          v17 = -1;
          do
            ++v17;
          while ( pwszFriendlyName[v17] );
          v18 = v17 + 1;
          v19 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v17 + 1));
          *a2 = v19;
          if ( v19 )
            Methods = StringCchCopyW(v19, v18, pEapMethods[v15].pwszFriendlyName);
          else
            Methods = -2147024882;
        }
LABEL_27:
        WpFreeProfile(v30);
        v8 = pEapError;
      }
      else
      {
        Methods = -2147024809;
      }
      pEapError = 0;
      if ( v8 )
        EapHostPeerFreeErrorMemory(v8);
      wil::details::FreeEapMethodInfoArray((wil::details *)&pEapMethodInfoArray, (struct _EAP_METHOD_INFO_ARRAY *)v8);
    }
    WlanFreeMemory(pstrProfileXml);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_660af29b5b58392da31645ec246aada0_Traceguids,
      (unsigned int)Methods);
  return (unsigned int)Methods;
}

```

## disassembly

```asm
0x18007502c  push    rbp
0x18007502e  push    rbx
0x18007502f  push    rsi
0x180075030  push    rdi
0x180075031  push    r13
0x180075033  push    r14
0x180075035  push    r15
0x180075037  mov     rbp, rsp
0x18007503a  sub     rsp, 80h
0x180075041  mov     r14, rdx
0x180075044  mov     rbx, rcx
0x180075047  mov     rcx, cs:WPP_GLOBAL_Control
0x18007504e  lea     r13, WPP_GLOBAL_Control
0x180075055  cmp     rcx, r13
0x180075058  jz      short loc_180075075
0x18007505a  test    byte ptr [rcx+1Ch], 40h
0x18007505e  jz      short loc_180075075
0x180075060  mov     rcx, [rcx+10h]
0x180075064  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x18007506b  mov     edx, 0Fh
0x180075070  call    WPP_SF_
0x180075075  xor     r15d, r15d
0x180075078  lea     rax, [rbp+arg_0]
0x18007507c  mov     [rsp+80h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180075081  lea     r8, [rbx+18h]; strProfileName
0x180075085  lea     rax, [rbp+arg_8]
0x180075089  mov     [r14], r15
0x18007508c  mov     rcx, [rbx]; hClientHandle
0x18007508f  lea     rdx, [rbx+8]; pInterfaceGuid
0x180075093  mov     [rsp+80h+pdwFlags], rax; pdwFlags
0x180075098  xor     r9d, r9d; pReserved
0x18007509b  lea     rax, [rbp+var_38]
0x18007509f  mov     [rbp+var_38], r15
0x1800750a3  mov     [rsp+80h+pstrProfileXml], rax; pstrProfileXml
0x1800750a8  mov     [rbp+arg_8], r15d
0x1800750ac  mov     [rbp+arg_0], r15d
0x1800750b0  call    cs:__imp_WlanGetProfile
0x1800750b6  mov     ebx, eax
0x1800750b8  test    eax, eax
0x1800750ba  jle     short loc_1800750C5
0x1800750bc  movzx   ebx, ax
0x1800750bf  or      ebx, 80070000h
0x1800750c5  test    ebx, ebx
0x1800750c7  js      loc_18007523D
0x1800750cd  mov     rcx, [rbp+var_38]
0x1800750d1  lea     r9, [rbp+arg_10]
0x1800750d5  xor     r8d, r8d
0x1800750d8  mov     [rbp+arg_18], r15
0x1800750dc  lea     rdx, [rbp+arg_18]
0x1800750e0  mov     [rbp+arg_10], r15d
0x1800750e4  call    cs:__imp_WpParseProfileXml
0x1800750ea  mov     ebx, eax
0x1800750ec  test    eax, eax
0x1800750ee  jle     short loc_1800750F9
0x1800750f0  movzx   ebx, ax
0x1800750f3  or      ebx, 80070000h
0x1800750f9  test    ebx, ebx
0x1800750fb  js      loc_180075233
0x180075101  mov     rax, [rbp+arg_18]
0x180075105  xorps   xmm0, xmm0
0x180075108  movups  xmmword ptr [rbp+pEapMethodInfoArray.dwNumberOfMethods], xmm0
0x18007510c  mov     rdx, r15
0x18007510f  mov     [rbp+pEapError], rdx
0x180075113  mov     rcx, [rax+228h]
0x18007511a  mov     rax, [rcx+20h]
0x18007511e  mov     rcx, [rax+1A8h]
0x180075125  cmp     [rcx+20h], r15d
0x180075129  jz      loc_180075213
0x18007512f  mov     rsi, [rcx+30h]
0x180075133  lea     rax, [rbp+pEapError]
0x180075137  lea     rdx, [rbp+ppEapError]; ppEapError
0x18007513b  mov     [rbp+var_20], rax
0x18007513f  lea     rcx, [rbp+pEapMethodInfoArray]; pEapMethodInfoArray
0x180075143  mov     [rbp+ppEapError], r15
0x180075147  mov     [rbp+var_10], 1
0x18007514b  mov     edi, [rsi+40h]
0x18007514e  call    cs:__imp_EapHostPeerGetMethods
0x180075154  lea     rcx, [rbp+var_20]
0x180075158  mov     ebx, eax
0x18007515a  call    ??1?$out_param_t@V?$unique_ptr@U_EAP_ERROR@@U?$function_deleter@P6AXPEAU_EAP_ERROR@@@Z$1?EapHostPeerFreeErrorMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&EapHostPeerFreeErrorMemory(_EAP_ERROR *)>>>::~out_param_t<wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&EapHostPeerFreeErrorMemory(_EAP_ERROR *)>>>(void)
0x18007515f  test    ebx, ebx
0x180075161  jnz     loc_1800751F8
0x180075167  mov     edx, edi
0x180075169  mov     ecx, r15d
0x18007516c  mov     rdi, [rbp+pEapMethodInfoArray.pEapMethods]
0x180075170  cmp     ecx, [rbp+pEapMethodInfoArray.dwNumberOfMethods]
0x180075173  jnb     short loc_1800751EA
0x180075175  mov     eax, ecx
0x180075177  lea     rbx, [rax+rax*2]
0x18007517b  mov     al, [rdx+rsi+4]
0x18007517f  add     rbx, rbx
0x180075182  cmp     [rdi+rbx*8], al
0x180075185  jnz     short loc_18007519B
0x180075187  mov     eax, [rdx+rsi+8]
0x18007518b  cmp     [rdi+rbx*8+4], eax
0x18007518f  jnz     short loc_18007519B
0x180075191  mov     eax, [rdx+rsi+10h]
0x180075195  cmp     [rdi+rbx*8+0Ch], eax
0x180075199  jz      short loc_18007519F
0x18007519b  inc     ecx
0x18007519d  jmp     short loc_180075170
0x18007519f  mov     rcx, [rdi+rbx*8+18h]
0x1800751a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800751a8  inc     rax
0x1800751ab  cmp     [rcx+rax*2], r15w
0x1800751b0  jnz     short loc_1800751A8
0x1800751b2  lea     rsi, [rax+1]
0x1800751b6  mov     ecx, 40h ; '@'; uFlags
0x1800751bb  lea     rdx, [rsi+rsi]; uBytes
0x1800751bf  call    cs:__imp_LocalAlloc
0x1800751c5  mov     [r14], rax
0x1800751c8  test    rax, rax
0x1800751cb  jz      short loc_1800751F1
0x1800751cd  mov     r8, [rdi+rbx*8+18h]; unsigned __int16 *
0x1800751d2  mov     rdx, rsi; unsigned __int64
0x1800751d5  mov     rcx, rax; unsigned __int16 *
0x1800751d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800751dd  mov     ebx, eax
0x1800751df  test    eax, eax
0x1800751e1  js      short loc_180075203
0x1800751e3  shr     eax, 1Fh
0x1800751e6  xor     al, 1
0x1800751e8  jnz     short loc_180075203
0x1800751ea  mov     ebx, 80070002h
0x1800751ef  jmp     short loc_180075203
0x1800751f1  mov     ebx, 8007000Eh
0x1800751f6  jmp     short loc_180075203
0x1800751f8  jle     short loc_180075203
0x1800751fa  movzx   ebx, bx
0x1800751fd  or      ebx, 80070000h
0x180075203  mov     rcx, [rbp+arg_18]
0x180075207  call    cs:__imp_WpFreeProfile
0x18007520d  mov     rdx, [rbp+pEapError]
0x180075211  jmp     short loc_180075218
0x180075213  mov     ebx, 80070057h
0x180075218  mov     [rbp+pEapError], r15
0x18007521c  test    rdx, rdx
0x18007521f  jz      short loc_18007522A
0x180075221  mov     rcx, rdx; pEapError
0x180075224  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18007522a  lea     rcx, [rbp+pEapMethodInfoArray]; this
0x18007522e  call    ?FreeEapMethodInfoArray@details@wil@@YAXPEAU_EAP_METHOD_INFO_ARRAY@@@Z; wil::details::FreeEapMethodInfoArray(_EAP_METHOD_INFO_ARRAY *)
0x180075233  mov     rcx, [rbp+var_38]; pMemory
0x180075237  call    cs:__imp_WlanFreeMemory
0x18007523d  mov     rcx, cs:WPP_GLOBAL_Control
0x180075244  cmp     rcx, r13
0x180075247  jz      short loc_180075267
0x180075249  test    byte ptr [rcx+1Ch], 40h
0x18007524d  jz      short loc_180075267
0x18007524f  mov     rcx, [rcx+10h]
0x180075253  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x18007525a  mov     edx, 10h
0x18007525f  mov     r9d, ebx
0x180075262  call    WPP_SF_d
0x180075267  mov     eax, ebx
0x180075269  add     rsp, 80h
0x180075270  pop     r15
0x180075272  pop     r14
0x180075274  pop     r13
0x180075276  pop     rdi
0x180075277  pop     rsi
0x180075278  pop     rbx
0x180075279  pop     rbp
0x18007527a  retn
```
