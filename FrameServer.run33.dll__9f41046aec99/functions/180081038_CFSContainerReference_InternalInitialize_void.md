# CFSContainerReference::InternalInitialize(void)

- ea: `0x180081038`
- end: `0x180081162`
- name: `?InternalInitialize@CFSContainerReference@@IEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(CFSContainerReference *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180080e34`

## callees

- `0x180005b94`
- `0x180005e78`
- `0x180009608`
- `0x180080d94`
- `0x180081038`

## import_xrefs

- `MFPlat!MFAllocateSerialWorkQueue` at `0x180081059`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x180081059`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800810bb`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800810bb`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1800810e4`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x1800810e4`

## pseudocode

```c
__int64 __fastcall CFSContainerReference::InternalInitialize(DWORD *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  _QWORD *v5; // rsi
  void *v6; // rbx
  char v8; // [rsp+60h] [rbp+8h] BYREF

  if ( !this[27] )
  {
    v2 = MFAllocateSerialWorkQueue(5u, this + 27);
    v3 = v2;
    if ( v2 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_14;
      v4 = 28;
      goto LABEL_13;
    }
  }
  v5 = this + 22;
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
    CFSContainerReference::CloseContainer(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
  }
  *v5 = 0;
  v2 = CmsOpenContainer(this + 17, 23, 33, this + 22);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_14;
    v4 = 29;
    goto LABEL_13;
  }
  v2 = CmsRegisterForContainerNotifications(
         *v5,
         tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>::on_result,
         0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_14;
    v4 = 30;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, v2);
LABEL_14:
    if ( byte_18010EC4D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 31, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, v3);
    return v3;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 32, &WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids, this, v2);
  return v3;
}

```

## disassembly

```asm
0x180081038  push    rbx
0x18008103a  push    rbp
0x18008103b  push    rsi
0x18008103c  push    rdi
0x18008103d  sub     rsp, 38h
0x180081041  lea     rdx, [rcx+6Ch]; pdwWorkQueue
0x180081045  mov     rdi, rcx
0x180081048  cmp     dword ptr [rdx], 0
0x18008104b  lea     rbp, WPP_cb07d43c516b3c9f6415f7501f7e13b4_Traceguids
0x180081052  jnz     short loc_18008107C
0x180081054  mov     ecx, 5; dwWorkQueue
0x180081059  call    cs:__imp_MFAllocateSerialWorkQueue
0x18008105f  mov     ebx, eax
0x180081061  test    eax, eax
0x180081063  jns     short loc_18008107C
0x180081065  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008106c  jb      loc_180081118
0x180081072  mov     edx, 1Ch
0x180081077  jmp     loc_1800810FE
0x18008107c  lea     rsi, [rdi+58h]
0x180081080  mov     rbx, [rsi]
0x180081083  test    rbx, rbx
0x180081086  jz      short loc_1800810A4
0x180081088  lea     rcx, [rsp+58h+arg_0]; this
0x18008108d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180081092  mov     rcx, rbx; void *
0x180081095  call    ?CloseContainer@CFSContainerReference@@CAXPEAX@Z; CFSContainerReference::CloseContainer(void *)
0x18008109a  lea     rcx, [rsp+58h+arg_0]; this
0x18008109f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800810a4  mov     edx, 17h
0x1800810a9  mov     qword ptr [rsi], 0
0x1800810b0  lea     rcx, [rdi+44h]
0x1800810b4  mov     r9, rsi
0x1800810b7  lea     r8d, [rdx+0Ah]
0x1800810bb  call    cs:__imp_CmsOpenContainer
0x1800810c1  mov     ebx, eax
0x1800810c3  test    eax, eax
0x1800810c5  jns     short loc_1800810D7
0x1800810c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800810ce  jb      short loc_180081118
0x1800810d0  mov     edx, 1Dh
0x1800810d5  jmp     short loc_1800810FE
0x1800810d7  mov     rcx, [rsi]
0x1800810da  lea     rdx, ?on_result@?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>::on_result(TipReportingInfo const &)
0x1800810e1  xor     r8d, r8d
0x1800810e4  call    cs:__imp_CmsRegisterForContainerNotifications
0x1800810ea  mov     ebx, eax
0x1800810ec  test    eax, eax
0x1800810ee  jns     short loc_18008112C
0x1800810f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800810f7  jb      short loc_180081118
0x1800810f9  mov     edx, 1Eh
0x1800810fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180081105  mov     r9, rdi
0x180081108  mov     r8, rbp
0x18008110b  mov     [rsp+58h+var_38], eax
0x18008110f  mov     rcx, [rcx+10h]
0x180081113  call    WPP_SF_qD
0x180081118  cmp     cs:byte_18010EC4D, 1
0x18008111f  jb      short loc_180081157
0x180081121  mov     edx, 1Fh
0x180081126  mov     [rsp+58h+var_38], ebx
0x18008112a  jmp     short loc_18008113E
0x18008112c  cmp     cs:byte_18010EC4D, 10h
0x180081133  jb      short loc_180081157
0x180081135  mov     edx, 20h ; ' '
0x18008113a  mov     [rsp+58h+var_38], eax
0x18008113e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081145  mov     r9, rdi
0x180081148  mov     r8, rbp
0x18008114b  mov     rcx, [rcx+0D8h]
0x180081152  call    WPP_SF_qD
0x180081157  mov     eax, ebx
0x180081159  add     rsp, 38h
0x18008115d  pop     rdi
0x18008115e  pop     rsi
0x18008115f  pop     rbp
0x180081160  pop     rbx
0x180081161  retn
```
