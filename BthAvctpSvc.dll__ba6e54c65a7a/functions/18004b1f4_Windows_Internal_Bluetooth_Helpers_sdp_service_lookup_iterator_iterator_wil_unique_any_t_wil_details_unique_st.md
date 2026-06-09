# Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,ulong)

- ea: `0x18004b1f4`
- end: `0x18004b412`
- name: `??0iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `542`
- prototype: `__int64 __fastcall(__int64, HANDLE *, DWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18004ba18`

## callees

- `0x180002838`
- `0x1800029cc`
- `0x18001fe5c`
- `0x18003f834`
- `0x18003f9a8`
- `0x18004b1f4`
- `0x18004b418`
- `0x18004b608`
- `0x18004bd54`
- `0x18004bda8`

## import_xrefs

- `WS2_32!WSALookupServiceNextW` at `0x18004b283`
- `WS2_32!WSALookupServiceNextW` at `0x18004b32d`
- `WS2_32!WSALookupServiceNextW` at `0x18004b283`
- `WS2_32!WSALookupServiceNextW` at `0x18004b32d`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b292`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b2b5`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b34e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b292`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b2b5`
- `WS2_32!__imp_WSAGetLastError` at `0x18004b34e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::iterator(
        __int64 a1,
        HANDLE *a2,
        DWORD a3)
{
  PVOID *v6; // rcx
  struct _WSAQuerySetW *v7; // rdi
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  _BYTE v12[8]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-61h] BYREF
  _WSAQuerySetW qsResults; // [rsp+40h] [rbp-59h] BYREF
  DWORD dwBufferLength; // [rsp+108h] [rbp+6Fh] BYREF
  struct _WSAQuerySetW *v16; // [rsp+118h] [rbp+7Fh] BYREF

  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_BYTE *)(a1 + 28) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 21);
  *(_QWORD *)&qsResults.dwSize = 120;
  memset_0(&qsResults.lpszServiceInstanceName, 0, 0x70u);
  dwBufferLength = 120;
  if ( WSALookupServiceNextW(*a2, a3, &dwBufferLength, &qsResults) != -1 || WSAGetLastError() == 10014 )
  {
    v7 = (struct _WSAQuerySetW *)operator new[](dwBufferLength);
    v16 = v7;
    if ( WSALookupServiceNextW(*a2, a3, &dwBufferLength, v7) == -1 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_23;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WSAGetLastError();
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || *((_BYTE *)v8 + 25) < 5u )
        goto LABEL_23;
      v9 = 25;
    }
    else
    {
      v10 = Windows::Internal::Bluetooth::Helpers::sdp_service::sdp_service(
              (Windows::Internal::Bluetooth::Helpers::sdp_service *)v12,
              v7->lpBlob->pBlobData,
              v7->lpBlob->cbSize);
      Windows::Internal::Bluetooth::Helpers::sdp_service::operator=(a1, v10);
      wil::details::unique_storage<wil::details::resource_policy<_SDP_TREE_ROOT_NODE *,long (*)(_SDP_TREE_ROOT_NODE *),&long SdpFreeTree(_SDP_TREE_ROOT_NODE *),wistd::integral_constant<unsigned __int64,0>,_SDP_TREE_ROOT_NODE *,_SDP_TREE_ROOT_NODE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SDP_TREE_ROOT_NODE *,long (*)(_SDP_TREE_ROOT_NODE *),&long SdpFreeTree(_SDP_TREE_ROOT_NODE *),wistd::integral_constant<unsigned __int64,0>,_SDP_TREE_ROOT_NODE *,_SDP_TREE_ROOT_NODE *,0,std::nullptr_t>>(v13);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
        a1 + 16,
        a2);
      *(_DWORD *)(a1 + 24) = a3;
      *(_BYTE *)(a1 + 28) = 1;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_23;
      v9 = 26;
    }
    WPP_SF_sq(v8[2], v9);
LABEL_23:
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v16);
    return a1;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WSAGetLastError();
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 5u )
      WPP_SF_sq(v6[2], 23);
  }
  return a1;
}

```

## disassembly

```asm
0x18004b1f4  mov     [rsp-8+arg_0], rcx
0x18004b1f9  push    rbp
0x18004b1fa  push    rbx
0x18004b1fb  push    rsi
0x18004b1fc  push    rdi
0x18004b1fd  push    r12
0x18004b1ff  push    r14
0x18004b201  push    r15
0x18004b203  lea     rbp, [rsp-27h]
0x18004b208  sub     rsp, 0C0h
0x18004b20f  mov     esi, r8d
0x18004b212  mov     r14, rdx
0x18004b215  mov     rbx, rcx
0x18004b218  mov     byte ptr [rcx], 0
0x18004b21b  mov     qword ptr [rcx+8], 0
0x18004b223  mov     qword ptr [rcx+10h], 0
0x18004b22b  mov     byte ptr [rcx+1Ch], 0
0x18004b22f  lea     r12, WPP_GLOBAL_Control
0x18004b236  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b23d  cmp     rcx, r12
0x18004b240  jz      short loc_18004B25B
0x18004b242  cmp     byte ptr [rcx+19h], 5
0x18004b246  jb      short loc_18004B25B
0x18004b248  mov     edx, 15h
0x18004b24d  mov     [rsp+0F0h+var_D0], rbx
0x18004b252  mov     rcx, [rcx+10h]
0x18004b256  call    WPP_SF_sq
0x18004b25b  mov     edi, 78h ; 'x'
0x18004b260  mov     qword ptr [rbp+57h+qsResults.dwSize], rdi
0x18004b264  xor     edx, edx; Val
0x18004b266  lea     r8d, [rdi-8]; Size
0x18004b26a  lea     rcx, [rbp+57h+qsResults.lpszServiceInstanceName]; void *
0x18004b26e  call    memset_0
0x18004b273  mov     [rbp+57h+dwBufferLength], edi
0x18004b276  lea     r9, [rbp+57h+qsResults]; lpqsResults
0x18004b27a  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18004b27e  mov     edx, esi; dwControlFlags
0x18004b280  mov     rcx, [r14]; hLookup
0x18004b283  call    cs:__imp_WSALookupServiceNextW
0x18004b289  cmp     eax, 0FFFFFFFFh
0x18004b28c  jnz     loc_18004B312
0x18004b292  call    cs:__imp_WSAGetLastError
0x18004b298  cmp     eax, 271Eh
0x18004b29d  jz      short loc_18004B312
0x18004b29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b2a6  cmp     rcx, r12
0x18004b2a9  jz      loc_18004B3FD
0x18004b2af  cmp     byte ptr [rcx+19h], 4
0x18004b2b3  jb      short loc_18004B2E7
0x18004b2b5  call    cs:__imp_WSAGetLastError
0x18004b2bb  test    eax, eax
0x18004b2bd  jle     short loc_18004B2C7
0x18004b2bf  movzx   eax, ax
0x18004b2c2  or      eax, 80070000h
0x18004b2c7  mov     edx, 16h
0x18004b2cc  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18004b2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b2d7  mov     rcx, [rcx+10h]
0x18004b2db  call    WPP_SF_sd
0x18004b2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b2e7  cmp     rcx, r12
0x18004b2ea  jz      loc_18004B3FD
0x18004b2f0  cmp     byte ptr [rcx+19h], 5
0x18004b2f4  jb      loc_18004B3FD
0x18004b2fa  mov     edx, 17h
0x18004b2ff  mov     [rsp+0F0h+var_D0], rbx
0x18004b304  mov     rcx, [rcx+10h]
0x18004b308  call    WPP_SF_sq
0x18004b30d  jmp     loc_18004B3FD
0x18004b312  mov     ecx, [rbp+57h+dwBufferLength]; unsigned __int64
0x18004b315  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004b31a  mov     rdi, rax
0x18004b31d  mov     [rbp+57h+arg_18], rax
0x18004b321  mov     r9, rax; lpqsResults
0x18004b324  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18004b328  mov     edx, esi; dwControlFlags
0x18004b32a  mov     rcx, [r14]; hLookup
0x18004b32d  call    cs:__imp_WSALookupServiceNextW
0x18004b333  cmp     eax, 0FFFFFFFFh
0x18004b336  jnz     short loc_18004B392
0x18004b338  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b33f  cmp     rcx, r12
0x18004b342  jz      loc_18004B3F3
0x18004b348  cmp     byte ptr [rcx+19h], 3
0x18004b34c  jb      short loc_18004B380
0x18004b34e  call    cs:__imp_WSAGetLastError
0x18004b354  test    eax, eax
0x18004b356  jle     short loc_18004B360
0x18004b358  movzx   eax, ax
0x18004b35b  or      eax, 80070000h
0x18004b360  mov     edx, 18h
0x18004b365  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18004b369  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b370  mov     rcx, [rcx+10h]
0x18004b374  call    WPP_SF_sd
0x18004b379  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b380  cmp     rcx, r12
0x18004b383  jz      short loc_18004B3F3
0x18004b385  cmp     byte ptr [rcx+19h], 5
0x18004b389  jb      short loc_18004B3F3
0x18004b38b  mov     edx, 19h
0x18004b390  jmp     short loc_18004B3E4
0x18004b392  mov     rdx, [rdi+70h]
0x18004b396  mov     r8d, [rdx]; unsigned __int64
0x18004b399  mov     rdx, [rdx+8]; unsigned __int8 *
0x18004b39d  lea     rcx, [rbp+57h+var_C0]; this
0x18004b3a1  call    ??0sdp_service@Helpers@Bluetooth@Internal@Windows@@QEAA@PEAE_K@Z; Windows::Internal::Bluetooth::Helpers::sdp_service::sdp_service(uchar *,unsigned __int64)
0x18004b3a6  mov     rdx, rax
0x18004b3a9  mov     rcx, rbx
0x18004b3ac  call    ??4sdp_service@Helpers@Bluetooth@Internal@Windows@@QEAAAEAV01234@$$QEAV01234@@Z; Windows::Internal::Bluetooth::Helpers::sdp_service::operator=(Windows::Internal::Bluetooth::Helpers::sdp_service &&)
0x18004b3b1  lea     rcx, [rbp+57h+var_B8]
0x18004b3b5  call    ??1?$unique_storage@U?$resource_policy@PEAU_SDP_TREE_ROOT_NODE@@P6AJPEAU1@@Z$1?SdpFreeTree@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SDP_TREE_ROOT_NODE *,long (*)(_SDP_TREE_ROOT_NODE *),&SdpFreeTree(_SDP_TREE_ROOT_NODE *),wistd::integral_constant<unsigned __int64,0>,_SDP_TREE_ROOT_NODE *,_SDP_TREE_ROOT_NODE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SDP_TREE_ROOT_NODE *,long (*)(_SDP_TREE_ROOT_NODE *),&SdpFreeTree(_SDP_TREE_ROOT_NODE *),wistd::integral_constant<unsigned __int64,0>,_SDP_TREE_ROOT_NODE *,_SDP_TREE_ROOT_NODE *,0,std::nullptr_t>>(void)
0x18004b3ba  mov     rdx, r14
0x18004b3bd  lea     rcx, [rbx+10h]
0x18004b3c1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WSALookupServiceEnd@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WSALookupServiceEnd(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x18004b3c6  mov     [rbx+18h], esi
0x18004b3c9  mov     byte ptr [rbx+1Ch], 1
0x18004b3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b3d4  cmp     rcx, r12
0x18004b3d7  jz      short loc_18004B3F3
0x18004b3d9  cmp     byte ptr [rcx+19h], 5
0x18004b3dd  jb      short loc_18004B3F3
0x18004b3df  mov     edx, 1Ah
0x18004b3e4  mov     [rsp+0F0h+var_D0], rbx
0x18004b3e9  mov     rcx, [rcx+10h]
0x18004b3ed  call    WPP_SF_sq
0x18004b3f2  nop
0x18004b3f3  lea     rcx, [rbp+57h+arg_18]
0x18004b3f7  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18004b3fc  nop
0x18004b3fd  mov     rax, rbx
0x18004b400  add     rsp, 0C0h
0x18004b407  pop     r15
0x18004b409  pop     r14
0x18004b40b  pop     r12
0x18004b40d  pop     rdi
0x18004b40e  pop     rsi
0x18004b40f  pop     rbx
0x18004b410  pop     rbp
0x18004b411  retn
```
