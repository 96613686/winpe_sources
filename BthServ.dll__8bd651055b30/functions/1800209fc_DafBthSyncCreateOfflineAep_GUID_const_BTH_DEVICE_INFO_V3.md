# DafBthSyncCreateOfflineAep(_GUID const *,_BTH_DEVICE_INFO_V3 *)

- ea: `0x1800209fc`
- end: `0x180020cbd`
- name: `?DafBthSyncCreateOfflineAep@@YAJPEBU_GUID@@PEAU_BTH_DEVICE_INFO_V3@@@Z`
- size: `705`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _BTH_DEVICE_INFO_V3 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002103c`

## callees

- `0x180001790`
- `0x1800209fc`
- `0x180021ac8`
- `0x180021b88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020a79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020a79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020ba7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020bf6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020ba7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020bf6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020bcf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c51`
- `deviceassociation!DafMemFree` at `0x180020c30`
- `deviceassociation!DafMemFree` at `0x180020c30`
- `deviceassociation!DafStartFinalize` at `0x180020be4`
- `deviceassociation!DafStartFinalize` at `0x180020be4`
- `deviceassociation!DafSelectCeremony` at `0x180020bbf`
- `deviceassociation!DafSelectCeremony` at `0x180020bbf`
- `deviceassociation!DafStartEnumCeremonies` at `0x180020b92`
- `deviceassociation!DafStartEnumCeremonies` at `0x180020b92`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x180020b45`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x180020b45`
- `deviceassociation!DafCloseAssociationContext` at `0x180020c0f`
- `deviceassociation!DafCloseAssociationContext` at `0x180020c0f`

## pseudocode

```c
__int64 __fastcall DafBthSyncCreateOfflineAep(const struct _GUID *a1, struct _BTH_DEVICE_INFO_V3 *a2)
{
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  signed int started; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  bool v11; // cf
  HANDLE hHandle[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v14; // [rsp+58h] [rbp+Fh]
  __int128 v15; // [rsp+60h] [rbp+17h] BYREF
  __int128 v16; // [rsp+70h] [rbp+27h]
  int v17; // [rsp+80h] [rbp+37h]

  v15 = 0;
  v17 = 0;
  v16 = 0;
  v14 = 0;
  *(_OWORD *)hHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  hHandle[0] = CreateEventW(0, 1, 0, 0);
  if ( hHandle[0] )
  {
    WORD5(v15) = 0;
    WORD2(v15) = 32;
    *((_QWORD *)&v16 + 1) = *((_QWORD *)a2 + 1);
    DWORD1(v16) = *(_DWORD *)a2;
    v17 = *((_DWORD *)a2 + 4);
    LODWORD(v15) = 0;
    *(_DWORD *)((char *)&v15 + 6) = 0;
    HIDWORD(v15) = 458519;
    LODWORD(v16) = 2;
    started = DafCreateAssociationContextFromOobBlob(a1, 36, &v15);
    if ( started >= 0 )
    {
      started = DafStartEnumCeremonies(0, 0, 0, DafBthSyncEnumCeremoniesCompleteCallback, hHandle);
      if ( started >= 0 )
      {
        WaitForSingleObject(hHandle[0], 0xFFFFFFFF);
        started = (signed int)hHandle[1];
        if ( SLODWORD(hHandle[1]) >= 0 )
        {
          started = DafSelectCeremony(0, &DAF_Ceremony_JustWorks);
          if ( started >= 0 )
          {
            ResetEvent(hHandle[0]);
            started = DafStartFinalize(0, &DafBthSyncFinalizeCompleteCallback, hHandle);
            if ( started >= 0 )
              WaitForSingleObject(hHandle[0], 0xFFFFFFFF);
          }
        }
      }
      goto LABEL_20;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 50;
      goto LABEL_10;
    }
  }
  else
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 49;
LABEL_10:
      WPP_SF_sd(v8[2], v9, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
LABEL_20:
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( v14 )
  {
    DafMemFree(v14, v5, v6);
    v8 = WPP_GLOBAL_Control;
    v14 = 0;
  }
  if ( hHandle[0] )
  {
    CloseHandle(hHandle[0]);
    v8 = WPP_GLOBAL_Control;
    hHandle[0] = 0;
  }
  v10 = 0;
  if ( started )
    v11 = *((_BYTE *)v8 + 25) < 2u;
  else
    v11 = *((_BYTE *)v8 + 25) < 5u;
  if ( v8 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v10) = !v11;
    if ( v10 )
      WPP_SF_sd(v8[2], 51, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800209fc  mov     [rsp-8+arg_10], rbx
0x180020a01  push    rbp
0x180020a02  push    rdi
0x180020a03  push    r12
0x180020a05  lea     rbp, [rsp-47h]
0x180020a0a  sub     rsp, 90h
0x180020a11  mov     rax, cs:__security_cookie
0x180020a18  xor     rax, rsp
0x180020a1b  mov     [rbp+57h+var_18], rax
0x180020a1f  xorps   xmm0, xmm0
0x180020a22  xor     eax, eax
0x180020a24  movups  [rbp+57h+var_40], xmm0
0x180020a28  mov     [rbp+57h+var_20], eax
0x180020a2b  mov     rbx, rdx
0x180020a2e  movups  [rbp+57h+var_30], xmm0
0x180020a32  mov     [rbp+57h+var_48], rax
0x180020a36  mov     rdi, rcx
0x180020a39  mov     [rbp+57h+var_60], rax
0x180020a3d  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x180020a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a48  lea     r12, WPP_GLOBAL_Control
0x180020a4f  cmp     rcx, r12
0x180020a52  jz      short loc_180020A6D
0x180020a54  cmp     byte ptr [rcx+19h], 5
0x180020a58  jb      short loc_180020A6D
0x180020a5a  mov     rcx, [rcx+10h]
0x180020a5e  lea     edx, [rax+30h]
0x180020a61  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180020a68  call    WPP_SF_s
0x180020a6d  xor     r9d, r9d; lpName
0x180020a70  xor     r8d, r8d; bInitialState
0x180020a73  xor     ecx, ecx; lpEventAttributes
0x180020a75  lea     edx, [r9+1]; bManualReset
0x180020a79  call    cs:__imp_CreateEventW
0x180020a7f  mov     [rbp+57h+hHandle], rax
0x180020a83  test    rax, rax
0x180020a86  jnz     short loc_180020AD5
0x180020a88  call    cs:__imp_GetLastError
0x180020a8e  mov     ebx, eax
0x180020a90  test    eax, eax
0x180020a92  jle     short loc_180020A9D
0x180020a94  movzx   ebx, ax
0x180020a97  or      ebx, 80070000h
0x180020a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aa4  cmp     rcx, r12
0x180020aa7  jz      loc_180020C03
0x180020aad  cmp     byte ptr [rcx+19h], 2
0x180020ab1  jb      loc_180020C03
0x180020ab7  mov     edx, 31h ; '1'
0x180020abc  mov     dword ptr [rsp+0A0h+var_80], ebx
0x180020ac0  mov     rcx, [rcx+10h]
0x180020ac4  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180020acb  call    WPP_SF_sd
0x180020ad0  jmp     loc_180020BFC
0x180020ad5  xor     eax, eax
0x180020ad7  mov     [rsp+0A0h+var_68], 0
0x180020ae0  mov     word ptr [rbp+57h+var_40+0Ah], ax
0x180020ae4  lea     r8, [rbp+57h+var_40]
0x180020ae8  mov     eax, 20h ; ' '
0x180020aed  mov     [rsp+0A0h+var_70], 0
0x180020af6  mov     word ptr [rbp+57h+var_40+4], ax
0x180020afa  xor     r9d, r9d
0x180020afd  mov     rax, [rbx+8]
0x180020b01  mov     rcx, rdi
0x180020b04  mov     qword ptr [rbp+57h+var_30+8], rax
0x180020b08  mov     eax, [rbx]
0x180020b0a  mov     dword ptr [rbp+57h+var_30+4], eax
0x180020b0d  lea     edx, [r9+24h]
0x180020b11  mov     eax, [rbx+10h]
0x180020b14  mov     [rbp+57h+var_20], eax
0x180020b17  lea     rax, [rbp+57h+var_60]
0x180020b1b  mov     [rsp+0A0h+var_78], rax
0x180020b20  lea     rax, [rbp+57h+var_48]
0x180020b24  mov     [rsp+0A0h+var_80], rax
0x180020b29  mov     dword ptr [rbp+57h+var_40], 0
0x180020b30  mov     dword ptr [rbp+57h+var_40+6], 0
0x180020b37  mov     dword ptr [rbp+57h+var_40+0Ch], 6FF17h
0x180020b3e  mov     dword ptr [rbp+57h+var_30], 2
0x180020b45  call    cs:__imp_DafCreateAssociationContextFromOobBlob
0x180020b4b  mov     ebx, eax
0x180020b4d  test    eax, eax
0x180020b4f  jns     short loc_180020B79
0x180020b51  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b58  cmp     rcx, r12
0x180020b5b  jz      loc_180020C03
0x180020b61  cmp     byte ptr [rcx+19h], 2
0x180020b65  jb      loc_180020C03
0x180020b6b  mov     edx, 32h ; '2'
0x180020b70  mov     dword ptr [rsp+0A0h+var_80], eax
0x180020b74  jmp     loc_180020AC0
0x180020b79  mov     rcx, [rbp+57h+var_60]
0x180020b7d  lea     rax, [rbp+57h+hHandle]
0x180020b81  lea     r9, ?DafBthSyncEnumCeremoniesCompleteCallback@@YAXKPEBU_CEREMONY@@PEAXJ@Z; DafBthSyncEnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)
0x180020b88  mov     [rsp+0A0h+var_80], rax
0x180020b8d  xor     r8d, r8d
0x180020b90  xor     edx, edx
0x180020b92  call    cs:__imp_DafStartEnumCeremonies
0x180020b98  mov     ebx, eax
0x180020b9a  test    eax, eax
0x180020b9c  js      short loc_180020BFC
0x180020b9e  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180020ba2  or      edi, 0FFFFFFFFh
0x180020ba5  mov     edx, edi; dwMilliseconds
0x180020ba7  call    cs:__imp_WaitForSingleObject
0x180020bad  mov     ebx, dword ptr [rbp+57h+hHandle+8]
0x180020bb0  test    ebx, ebx
0x180020bb2  js      short loc_180020BFC
0x180020bb4  mov     rcx, [rbp+57h+var_60]
0x180020bb8  lea     rdx, DAF_Ceremony_JustWorks
0x180020bbf  call    cs:__imp_DafSelectCeremony
0x180020bc5  mov     ebx, eax
0x180020bc7  test    eax, eax
0x180020bc9  js      short loc_180020BFC
0x180020bcb  mov     rcx, [rbp+57h+hHandle]; hEvent
0x180020bcf  call    cs:__imp_ResetEvent
0x180020bd5  mov     rcx, [rbp+57h+var_60]
0x180020bd9  lea     r8, [rbp+57h+hHandle]
0x180020bdd  lea     rdx, ?DafBthSyncFinalizeCompleteCallback@@YAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; DafBthSyncFinalizeCompleteCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x180020be4  call    cs:__imp_DafStartFinalize
0x180020bea  mov     ebx, eax
0x180020bec  test    eax, eax
0x180020bee  js      short loc_180020BFC
0x180020bf0  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180020bf4  mov     edx, edi; dwMilliseconds
0x180020bf6  call    cs:__imp_WaitForSingleObject
0x180020bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c03  mov     rax, [rbp+57h+var_60]
0x180020c07  test    rax, rax
0x180020c0a  jz      short loc_180020C24
0x180020c0c  mov     rcx, rax
0x180020c0f  call    cs:__imp_DafCloseAssociationContext
0x180020c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c1c  mov     [rbp+57h+var_60], 0
0x180020c24  mov     rax, [rbp+57h+var_48]
0x180020c28  test    rax, rax
0x180020c2b  jz      short loc_180020C45
0x180020c2d  mov     rcx, rax
0x180020c30  call    cs:__imp_DafMemFree
0x180020c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c3d  mov     [rbp+57h+var_48], 0
0x180020c45  mov     rax, [rbp+57h+hHandle]
0x180020c49  test    rax, rax
0x180020c4c  jz      short loc_180020C66
0x180020c4e  mov     rcx, rax; hObject
0x180020c51  call    cs:__imp_CloseHandle
0x180020c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c5e  mov     [rbp+57h+hHandle], 0
0x180020c66  xor     eax, eax
0x180020c68  test    ebx, ebx
0x180020c6a  jnz     short loc_180020C72
0x180020c6c  cmp     byte ptr [rcx+19h], 5
0x180020c70  jmp     short loc_180020C76
0x180020c72  cmp     byte ptr [rcx+19h], 2
0x180020c76  setnb   al
0x180020c79  cmp     rcx, r12
0x180020c7c  jz      short loc_180020C9B
0x180020c7e  test    eax, eax
0x180020c80  jz      short loc_180020C9B
0x180020c82  mov     rcx, [rcx+10h]
0x180020c86  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180020c8d  mov     edx, 33h ; '3'
0x180020c92  mov     dword ptr [rsp+0A0h+var_80], ebx
0x180020c96  call    WPP_SF_sd
0x180020c9b  mov     eax, ebx
0x180020c9d  mov     rcx, [rbp+57h+var_18]
0x180020ca1  xor     rcx, rsp; StackCookie
0x180020ca4  call    __security_check_cookie
0x180020ca9  mov     rbx, [rsp+0A0h+arg_10]
0x180020cb1  add     rsp, 90h
0x180020cb8  pop     r12
0x180020cba  pop     rdi
0x180020cbb  pop     rbp
0x180020cbc  retn
```
