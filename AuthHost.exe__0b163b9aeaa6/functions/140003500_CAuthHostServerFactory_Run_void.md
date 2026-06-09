# CAuthHostServerFactory::Run(void)

- ea: `0x140003500`
- end: `0x140003799`
- name: `?Run@CAuthHostServerFactory@@QEAAJXZ`
- size: `665`
- prototype: `__int64 __fastcall(CAuthHostServerFactory *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002dfc`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x140003500`
- `0x140003b70`
- `0x14000407c`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000365c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000365c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400035d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400035d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003775`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400035c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400035c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400036b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400036f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400036b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400036f9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003564`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003564`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003786`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003786`

## pseudocode

```c
__int64 __fastcall CAuthHostServerFactory::Run(CAuthHostServerFactory *this)
{
  unsigned int v2; // ebx
  struct IUnknown *v3; // rdx
  const struct _GUID *v4; // rcx
  signed int LastError; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int i; // edi
  int v9; // eax
  void *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h]

  v13 = 0;
  v14 = 0;
  if ( !hObject )
  {
    v2 = CoInitializeEx(0, 0);
    if ( (v2 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids, v2);
      }
      return v2;
    }
    hObject = CreateEventW(0, 0, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 16;
LABEL_19:
      WPP_SF_d(v6[7], v7, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids, v2);
LABEL_46:
      if ( qword_14001D0C8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_14001D0C8 + 16LL))(qword_14001D0C8);
        qword_14001D0C8 = 0;
      }
      UnregisterAuthHostProcess((struct _AUTH_HOST_REGISTER_CONTEXT *)&v13);
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      CoUninitialize();
      return v2;
    }
    for ( i = 1; ; ++i )
    {
      v9 = RegisterAuthHostProcess(v4, v3, (struct _AUTH_HOST_REGISTER_CONTEXT *)&v13);
      v2 = v9;
      if ( i >= 5 || v9 != -2147012892 && v9 != -2147023170 )
        break;
      Sleep(0x64u);
    }
    if ( v9 != 1 )
    {
      if ( v9 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
        {
          goto LABEL_46;
        }
        v7 = 17;
        goto LABEL_19;
      }
      if ( WaitForSingleObject(hObject, 0xFFFFFFFF) || !qword_14001D0C8 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
        {
          goto LABEL_45;
        }
        v12 = 18;
        goto LABEL_44;
      }
      v10 = *(void **)(qword_14001D0C8 + 16);
      if ( !v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
        {
          goto LABEL_45;
        }
        v12 = 19;
LABEL_44:
        WPP_SF_(v11[7], v12, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids);
LABEL_45:
        v2 = -2147164127;
        goto LABEL_46;
      }
      WaitForSingleObject(v10, 0xFFFFFFFF);
    }
    v2 = 0;
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids);
  }
  return 2147746294LL;
}

```

## disassembly

```asm
0x140003500  mov     [rsp+arg_0], rbx
0x140003505  push    rdi
0x140003506  sub     rsp, 40h
0x14000350a  xor     eax, eax
0x14000350c  xorps   xmm0, xmm0
0x14000350f  cmp     cs:hObject, rax
0x140003516  movups  [rsp+48h+var_28], xmm0
0x14000351b  mov     [rsp+48h+var_18], rax
0x140003520  jz      short loc_140003560
0x140003522  mov     rcx, cs:WPP_GLOBAL_Control
0x140003529  lea     rax, WPP_GLOBAL_Control
0x140003530  cmp     rcx, rax
0x140003533  jz      short loc_140003556
0x140003535  test    byte ptr [rcx+44h], 10h
0x140003539  jz      short loc_140003556
0x14000353b  cmp     byte ptr [rcx+41h], 2
0x14000353f  jb      short loc_140003556
0x140003541  mov     rcx, [rcx+38h]
0x140003545  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x14000354c  mov     edx, 0Eh
0x140003551  call    WPP_SF_
0x140003556  mov     eax, 800401F6h
0x14000355b  jmp     loc_14000378E
0x140003560  xor     edx, edx; dwCoInit
0x140003562  xor     ecx, ecx; pvReserved
0x140003564  call    cs:__imp_CoInitializeEx
0x14000356a  mov     ebx, eax
0x14000356c  test    eax, eax
0x14000356e  jns     short loc_1400035B8
0x140003570  mov     rcx, cs:WPP_GLOBAL_Control
0x140003577  lea     rax, WPP_GLOBAL_Control
0x14000357e  cmp     rcx, rax
0x140003581  jz      loc_14000378C
0x140003587  test    byte ptr [rcx+44h], 10h
0x14000358b  jz      loc_14000378C
0x140003591  cmp     byte ptr [rcx+41h], 2
0x140003595  jb      loc_14000378C
0x14000359b  mov     rcx, [rcx+38h]
0x14000359f  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x1400035a6  mov     edx, 0Fh
0x1400035ab  mov     r9d, ebx
0x1400035ae  call    WPP_SF_d
0x1400035b3  jmp     loc_14000378C
0x1400035b8  xor     r9d, r9d; lpName
0x1400035bb  xor     r8d, r8d; bInitialState
0x1400035be  xor     edx, edx; bManualReset
0x1400035c0  xor     ecx, ecx; lpEventAttributes
0x1400035c2  call    cs:__imp_CreateEventW
0x1400035c8  mov     cs:hObject, rax
0x1400035cf  test    rax, rax
0x1400035d2  jnz     short loc_140003631
0x1400035d4  call    cs:__imp_GetLastError
0x1400035da  mov     ebx, eax
0x1400035dc  test    eax, eax
0x1400035de  jle     short loc_1400035E9
0x1400035e0  movzx   ebx, ax
0x1400035e3  or      ebx, 80070000h
0x1400035e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035f0  lea     rax, WPP_GLOBAL_Control
0x1400035f7  cmp     rcx, rax
0x1400035fa  jz      loc_14000373C
0x140003600  test    byte ptr [rcx+44h], 10h
0x140003604  jz      loc_14000373C
0x14000360a  cmp     byte ptr [rcx+41h], 2
0x14000360e  jb      loc_14000373C
0x140003614  mov     edx, 10h
0x140003619  mov     rcx, [rcx+38h]
0x14000361d  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x140003624  mov     r9d, ebx
0x140003627  call    WPP_SF_d
0x14000362c  jmp     loc_14000373C
0x140003631  mov     edi, 1
0x140003636  lea     r8, [rsp+48h+var_28]; struct _AUTH_HOST_REGISTER_CONTEXT *
0x14000363b  call    ?RegisterAuthHostProcess@@YAJAEBU_GUID@@PEAUIUnknown@@PEAU_AUTH_HOST_REGISTER_CONTEXT@@@Z; RegisterAuthHostProcess(_GUID const &,IUnknown *,_AUTH_HOST_REGISTER_CONTEXT *)
0x140003640  mov     ebx, eax
0x140003642  cmp     edi, 5
0x140003645  jnb     short loc_140003664
0x140003647  cmp     eax, 80072EE4h
0x14000364c  jz      short loc_140003655
0x14000364e  cmp     eax, 800706BEh
0x140003653  jnz     short loc_140003664
0x140003655  inc     edi
0x140003657  mov     ecx, 64h ; 'd'; dwMilliseconds
0x14000365c  call    cs:__imp_Sleep
0x140003662  jmp     short loc_140003636
0x140003664  cmp     ebx, 1
0x140003667  jz      loc_1400036FF
0x14000366d  test    ebx, ebx
0x14000366f  jns     short loc_1400036A6
0x140003671  mov     rcx, cs:WPP_GLOBAL_Control
0x140003678  lea     rax, WPP_GLOBAL_Control
0x14000367f  cmp     rcx, rax
0x140003682  jz      loc_14000373C
0x140003688  test    byte ptr [rcx+44h], 10h
0x14000368c  jz      loc_14000373C
0x140003692  cmp     byte ptr [rcx+41h], 2
0x140003696  jb      loc_14000373C
0x14000369c  mov     edx, 11h
0x1400036a1  jmp     loc_140003619
0x1400036a6  mov     rcx, cs:hObject; hHandle
0x1400036ad  or      ebx, 0FFFFFFFFh
0x1400036b0  mov     edx, ebx; dwMilliseconds
0x1400036b2  call    cs:__imp_WaitForSingleObject
0x1400036b8  test    eax, eax
0x1400036ba  jnz     short loc_140003703
0x1400036bc  mov     rax, cs:qword_14001D0C8
0x1400036c3  test    rax, rax
0x1400036c6  jz      short loc_140003703
0x1400036c8  mov     rcx, [rax+10h]; hHandle
0x1400036cc  test    rcx, rcx
0x1400036cf  jnz     short loc_1400036F7
0x1400036d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036d8  lea     rax, WPP_GLOBAL_Control
0x1400036df  cmp     rcx, rax
0x1400036e2  jz      short loc_140003737
0x1400036e4  test    byte ptr [rcx+44h], 10h
0x1400036e8  jz      short loc_140003737
0x1400036ea  cmp     byte ptr [rcx+41h], 2
0x1400036ee  jb      short loc_140003737
0x1400036f0  mov     edx, 13h
0x1400036f5  jmp     short loc_140003727
0x1400036f7  mov     edx, ebx; dwMilliseconds
0x1400036f9  call    cs:__imp_WaitForSingleObject
0x1400036ff  xor     ebx, ebx
0x140003701  jmp     short loc_14000373C
0x140003703  mov     rcx, cs:WPP_GLOBAL_Control
0x14000370a  lea     rax, WPP_GLOBAL_Control
0x140003711  cmp     rcx, rax
0x140003714  jz      short loc_140003737
0x140003716  test    byte ptr [rcx+44h], 10h
0x14000371a  jz      short loc_140003737
0x14000371c  cmp     byte ptr [rcx+41h], 2
0x140003720  jb      short loc_140003737
0x140003722  mov     edx, 12h
0x140003727  mov     rcx, [rcx+38h]
0x14000372b  lea     r8, WPP_7c4350cd6e3a3fa521c812ffbe82d600_Traceguids
0x140003732  call    WPP_SF_
0x140003737  mov     ebx, 8004E021h
0x14000373c  mov     rcx, cs:qword_14001D0C8
0x140003743  test    rcx, rcx
0x140003746  jz      short loc_14000375F
0x140003748  mov     rax, [rcx]
0x14000374b  mov     rax, [rax+10h]
0x14000374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003754  mov     cs:qword_14001D0C8, 0
0x14000375f  lea     rcx, [rsp+48h+var_28]; struct _AUTH_HOST_REGISTER_CONTEXT *
0x140003764  call    ?UnregisterAuthHostProcess@@YAJPEAU_AUTH_HOST_REGISTER_CONTEXT@@@Z; UnregisterAuthHostProcess(_AUTH_HOST_REGISTER_CONTEXT *)
0x140003769  mov     rcx, cs:hObject; hObject
0x140003770  test    rcx, rcx
0x140003773  jz      short loc_140003786
0x140003775  call    cs:__imp_CloseHandle
0x14000377b  mov     cs:hObject, 0
0x140003786  call    cs:__imp_CoUninitialize
0x14000378c  mov     eax, ebx
0x14000378e  mov     rbx, [rsp+48h+arg_0]
0x140003793  add     rsp, 40h
0x140003797  pop     rdi
0x140003798  retn
```
