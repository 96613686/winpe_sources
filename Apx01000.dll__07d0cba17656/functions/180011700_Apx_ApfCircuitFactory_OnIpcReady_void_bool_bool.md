# Apx::ApfCircuitFactory::OnIpcReady(void *,bool,bool)

- ea: `0x180011700`
- end: `0x180011902`
- name: `?OnIpcReady@ApfCircuitFactory@Apx@@CAXPEAX_N1@Z`
- size: `514`
- prototype: `void __fastcall(char *, char, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002160`
- `0x180008fdc`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18000be74`
- `0x18000c7ec`
- `0x18000d044`
- `0x180011700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001186e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001186e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118d7`

## pseudocode

```c
void __fastcall Apx::ApfCircuitFactory::OnIpcReady(char *a1, char a2, char a3)
{
  char *v6; // rcx
  HANDLE v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  HANDLE v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE hObject; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v16; // [rsp+78h] [rbp+20h]

  v6 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
    v6 = (char *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  hObject = 0;
  if ( v6 != (char *)&WPP_GLOBAL_Control && v6[28] < 0 && (unsigned __int8)v6[25] >= 4u )
    WPP_SF_dd(*((_QWORD *)v6 + 2), 45, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  if ( a3 )
  {
LABEL_18:
    v9 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v9;
    if ( v9 )
    {
      v10 = v7;
      if ( a3 )
        v10 = 0;
      *v9 = &Apx::ApfCircuitFactory_IpcReadyProcess::`vftable';
      v9[1] = a1;
      *((_BYTE *)v9 + 16) = a2;
      v9[3] = v10;
      if ( (int)Apx::ApfWorkItemQueue::AddWorkItemToQueue(
                  (Apx::ApfWorkItemQueue *)(a1 + 168),
                  (struct Apx::ApfWorkItemBase *)v9) >= 0 )
      {
        if ( !a3 )
          WaitForSingleObject(v7, 0xFFFFFFFF);
        goto LABEL_34;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_39;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_35;
      v11 = 48;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_39;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_35;
      v11 = 47;
    }
    WPP_SF_d(v8[2], v11, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
    goto LABEL_34;
  }
  if ( (int)_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&hObject) >= 0 )
  {
    v7 = hObject;
    goto LABEL_18;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v7 = hObject;
    goto LABEL_39;
  }
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
    v7 = hObject;
LABEL_34:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v7 = hObject;
LABEL_35:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(v8[2], 49, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
LABEL_39:
  if ( v7 )
  {
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  }
}

```

## disassembly

```asm
0x180011700  mov     [rsp+arg_8], rbx
0x180011705  push    rbp
0x180011706  push    rsi
0x180011707  push    rdi
0x180011708  push    r12
0x18001170a  push    r14
0x18001170c  sub     rsp, 30h
0x180011710  movzx   edi, r8b
0x180011714  movzx   esi, dl
0x180011717  mov     rbp, rcx
0x18001171a  lea     r14, WPP_GLOBAL_Control
0x180011721  lea     r12, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180011728  mov     rcx, cs:WPP_GLOBAL_Control
0x18001172f  cmp     rcx, r14
0x180011732  jz      short loc_180011758
0x180011734  test    byte ptr [rcx+1Ch], 1
0x180011738  jz      short loc_180011758
0x18001173a  cmp     byte ptr [rcx+19h], 5
0x18001173e  jb      short loc_180011758
0x180011740  mov     edx, 2Ch ; ','
0x180011745  mov     r8, r12
0x180011748  mov     rcx, [rcx+10h]
0x18001174c  call    WPP_SF_
0x180011751  mov     rcx, cs:WPP_GLOBAL_Control
0x180011758  xor     ebx, ebx
0x18001175a  mov     [rsp+58h+hObject], rbx
0x18001175f  cmp     rcx, r14
0x180011762  jz      short loc_180011786
0x180011764  test    byte ptr [rcx+1Ch], 80h
0x180011768  jz      short loc_180011786
0x18001176a  cmp     byte ptr [rcx+19h], 4
0x18001176e  jb      short loc_180011786
0x180011770  mov     r9d, esi
0x180011773  lea     edx, [rbx+2Dh]
0x180011776  mov     [rsp+58h+var_38], edi
0x18001177a  mov     r8, r12
0x18001177d  mov     rcx, [rcx+10h]
0x180011781  call    WPP_SF_dd
0x180011786  test    dil, dil
0x180011789  jnz     short loc_1800117E8
0x18001178b  lea     rcx, [rsp+58h+hObject]
0x180011790  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011795  test    eax, eax
0x180011797  jns     short loc_1800117E3
0x180011799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117a0  cmp     rcx, r14
0x1800117a3  jz      short loc_1800117D9
0x1800117a5  test    byte ptr [rcx+1Ch], 80h
0x1800117a9  jz      short loc_1800117CF
0x1800117ab  cmp     byte ptr [rcx+19h], 2
0x1800117af  jb      short loc_1800117CF
0x1800117b1  mov     edx, 2Eh ; '.'
0x1800117b6  mov     r9d, eax
0x1800117b9  mov     r8, r12
0x1800117bc  mov     rcx, [rcx+10h]
0x1800117c0  call    WPP_SF_d
0x1800117c5  mov     rbx, [rsp+58h+hObject]
0x1800117ca  jmp     loc_1800118A5
0x1800117cf  mov     rbx, [rsp+58h+hObject]
0x1800117d4  jmp     loc_1800118AC
0x1800117d9  mov     rbx, [rsp+58h+hObject]
0x1800117de  jmp     loc_1800118CF
0x1800117e3  mov     rbx, [rsp+58h+hObject]
0x1800117e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800117ef  mov     ecx, 20h ; ' '; unsigned __int64
0x1800117f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800117f9  mov     rdx, rax; struct Apx::ApfWorkItemBase *
0x1800117fc  mov     [rsp+58h+arg_18], rax
0x180011801  test    rax, rax
0x180011804  jz      short loc_180011876
0x180011806  mov     rcx, rbx
0x180011809  xor     eax, eax
0x18001180b  test    dil, dil
0x18001180e  cmovnz  rcx, rax
0x180011812  lea     rax, ??_7ApfCircuitFactory_IpcReadyProcess@Apx@@6B@; const Apx::ApfCircuitFactory_IpcReadyProcess::`vftable'
0x180011819  mov     [rdx], rax
0x18001181c  mov     [rdx+8], rbp
0x180011820  mov     [rdx+10h], sil
0x180011824  mov     [rdx+18h], rcx
0x180011828  test    rdx, rdx
0x18001182b  jz      short loc_180011876
0x18001182d  lea     rcx, [rbp+0A8h]; this
0x180011834  call    ?AddWorkItemToQueue@ApfWorkItemQueue@Apx@@QEAAJPEAVApfWorkItemBase@2@@Z; Apx::ApfWorkItemQueue::AddWorkItemToQueue(Apx::ApfWorkItemBase *)
0x180011839  test    eax, eax
0x18001183b  jns     short loc_180011863
0x18001183d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011844  cmp     rcx, r14
0x180011847  jz      loc_1800118CF
0x18001184d  test    byte ptr [rcx+1Ch], 80h
0x180011851  jz      short loc_1800118AC
0x180011853  cmp     byte ptr [rcx+19h], 2
0x180011857  jb      short loc_1800118AC
0x180011859  mov     edx, 30h ; '0'
0x18001185e  mov     r9d, eax
0x180011861  jmp     short loc_180011899
0x180011863  test    dil, dil
0x180011866  jnz     short loc_1800118A5
0x180011868  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001186b  mov     rcx, rbx; hHandle
0x18001186e  call    cs:__imp_WaitForSingleObject
0x180011874  jmp     short loc_1800118A5
0x180011876  mov     rcx, cs:WPP_GLOBAL_Control
0x18001187d  cmp     rcx, r14
0x180011880  jz      short loc_1800118CF
0x180011882  test    byte ptr [rcx+1Ch], 80h
0x180011886  jz      short loc_1800118AC
0x180011888  cmp     byte ptr [rcx+19h], 2
0x18001188c  jb      short loc_1800118AC
0x18001188e  mov     edx, 2Fh ; '/'
0x180011893  mov     r9d, 8007000Eh
0x180011899  mov     r8, r12
0x18001189c  mov     rcx, [rcx+10h]
0x1800118a0  call    WPP_SF_d
0x1800118a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118ac  cmp     rcx, r14
0x1800118af  jz      short loc_1800118CF
0x1800118b1  test    byte ptr [rcx+1Ch], 1
0x1800118b5  jz      short loc_1800118CF
0x1800118b7  cmp     byte ptr [rcx+19h], 5
0x1800118bb  jb      short loc_1800118CF
0x1800118bd  mov     edx, 31h ; '1'
0x1800118c2  mov     r8, r12
0x1800118c5  mov     rcx, [rcx+10h]
0x1800118c9  call    WPP_SF_
0x1800118ce  nop
0x1800118cf  test    rbx, rbx
0x1800118d2  jz      short loc_1800118E1
0x1800118d4  mov     rcx, rbx; hObject
0x1800118d7  call    cs:__imp_CloseHandle
0x1800118dd  test    eax, eax
0x1800118df  jz      short loc_1800118F2
0x1800118e1  mov     rbx, [rsp+58h+arg_8]
0x1800118e6  add     rsp, 30h
0x1800118ea  pop     r14
0x1800118ec  pop     r12
0x1800118ee  pop     rdi
0x1800118ef  pop     rsi
0x1800118f0  pop     rbp
0x1800118f1  retn
0x1800118f2  mov     rcx, [rsp+58h]; this
0x1800118f7  mov     edx, 0A0Bh; void *
0x1800118fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
