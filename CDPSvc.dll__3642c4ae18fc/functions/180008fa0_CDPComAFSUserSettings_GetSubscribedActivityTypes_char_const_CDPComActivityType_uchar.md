# CDPComAFSUserSettings::GetSubscribedActivityTypes(char const *,CDPComActivityType * *,uchar *)

- ea: `0x180008fa0`
- end: `0x180009366`
- name: `?GetSubscribedActivityTypes@CDPComAFSUserSettings@@UEAAJPEBDPEAPEAW4CDPComActivityType@@PEAE@Z`
- size: `966`
- prototype: `__int64 __fastcall(CDPComAFSUserSettings *__hidden this, const char *, enum CDPComActivityType **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004928`
- `0x180008fa0`
- `0x18001a5b4`
- `0x18001ddf8`
- `0x180023148`
- `0x180026634`
- `0x180026758`
- `0x1800267cc`
- `0x180026834`
- `0x180026850`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateAFSUserSettingsInternal` at `0x18000903e`
- `cdp!CDPCreateAFSUserSettingsInternal` at `0x18000903e`

## string_xrefs

- `0x180008fe1`: `.\cdpcomafsusersettings.cpp`
- `0x18000905e`: `.\cdpcomafsusersettings.cpp`
- `0x18000925b`: `.\cdpcomafsusersettings.cpp`
- `0x1800092f7`: `.\cdpcomafsusersettings.cpp`

## pseudocode

```c
__int64 __fastcall CDPComAFSUserSettings::GetSubscribedActivityTypes(
        CDPComAFSUserSettings *this,
        const char *a2,
        enum CDPComActivityType **a3,
        unsigned __int8 *a4)
{
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  const char *v10; // r9
  _QWORD *v11; // rcx
  __int64 result; // rax
  __int64 v13; // rdi
  char *v14; // rsi
  unsigned __int64 v15; // rcx
  char *v16; // rax
  size_t v17; // rbx
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  unsigned __int8 v21; // dl
  char *v22; // rdi
  unsigned __int64 v23; // rcx
  char *v24; // rax
  size_t v25; // rbx
  int v26; // edx
  int v27; // ecx
  enum CDPComActivityType *v28; // rbx
  unsigned int v29; // [rsp+30h] [rbp-88h] BYREF
  int v30; // [rsp+34h] [rbp-84h] BYREF
  void *v31[2]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v32; // [rsp+48h] [rbp-70h]
  _QWORD *v33; // [rsp+50h] [rbp-68h] BYREF
  enum CDPComActivityType *v34; // [rsp+58h] [rbp-60h] BYREF
  __int128 v35; // [rsp+60h] [rbp-58h] BYREF
  char v36[32]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  unsigned int v38; // [rsp+C8h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v29 = 46;
LABEL_3:
    v38 = -2147024809;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v38 = -2147467261;
    v29 = 47;
LABEL_4:
    Log<long &,char const (&)[28],int>(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)&v38,
      (unsigned int)".\\cdpcomafsusersettings.cpp",
      (__int64)&v29);
    return v38;
  }
  if ( !a4 )
  {
    v29 = 48;
    goto LABEL_3;
  }
  v33 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v33);
  v7 = CDPCreateAFSUserSettingsInternal(a2, &v33);
  try
  {
    if ( v7 < 0 )
    {
      v29 = v7;
      v30 = 53;
      Log<long &,char const (&)[28],int>(
        v9,
        v8,
        (unsigned int)&v29,
        (unsigned int)".\\cdpcomafsusersettings.cpp",
        (__int64)&v30);
      v11 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v11 + 16LL))(v11, *v11);
      }
      return v29;
    }
    LOBYTE(v38) = 17;
    v13 = 0;
    while ( 1 )
    {
      std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(v31);
      v14 = (char *)v31[1];
      v15 = ((char *)v31[1] - (char *)v31[0]) >> 2;
      if ( (unsigned __int8)v38 >= v15 )
      {
        if ( (unsigned __int8)v38 <= v15 )
          goto LABEL_22;
        if ( (unsigned __int8)v38 > (unsigned __int64)((signed __int64)(v32 - (unsigned __int64)v31[0]) >> 2) )
        {
          std::vector<enum CDPActivityType>::_Resize_reallocate<std::_Value_init_tag>(v31, (unsigned __int8)v38);
          goto LABEL_22;
        }
        v17 = 4 * ((unsigned __int8)v38 - v15);
        memset_0(v31[1], 0, v17);
        v16 = &v14[v17];
      }
      else
      {
        v16 = (char *)v31[0] + 4 * (unsigned __int8)v38;
      }
      v31[1] = v16;
LABEL_22:
      v18 = (*(__int64 (__fastcall **)(_QWORD *, void *, unsigned int *))(*v33 + 32LL))(v33, v31[0], &v38);
      if ( v18 >= 0 )
      {
        v21 = v38;
        v22 = (char *)v31[1];
        v23 = ((char *)v31[1] - (char *)v31[0]) >> 2;
        if ( (unsigned __int8)v38 < v23 )
        {
          v24 = (char *)v31[0] + 4 * (unsigned __int8)v38;
          goto LABEL_29;
        }
        if ( (unsigned __int8)v38 > v23 )
        {
          if ( (unsigned __int8)v38 <= (unsigned __int64)((signed __int64)(v32 - (unsigned __int64)v31[0]) >> 2) )
          {
            v25 = 4 * ((unsigned __int8)v38 - v23);
            memset_0(v31[1], 0, v25);
            v24 = &v22[v25];
            v21 = v38;
LABEL_29:
            v31[1] = v24;
          }
          else
          {
            std::vector<enum CDPActivityType>::_Resize_reallocate<std::_Value_init_tag>(v31, (unsigned __int8)v38);
            v21 = v38;
          }
        }
        *a4 = v21;
        wil::make_unique_cotaskmem_nothrow<enum CDPComActivityType [0]>(&v34, v21);
        v28 = v34;
        if ( !v34 )
        {
          v29 = -2147024882;
          v30 = 69;
          Log<long &,char const (&)[28],int>(
            v27,
            v26,
            (unsigned int)&v29,
            (unsigned int)".\\cdpcomafsusersettings.cpp",
            (__int64)&v30);
          if ( v31[0] )
          {
            std::_Deallocate<16>(v31[0], (v32 - (unsigned __int64)v31[0]) & 0xFFFFFFFFFFFFFFFCuLL);
            *(_OWORD *)v31 = 0;
            v32 = 0;
          }
LABEL_36:
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v33);
          return v29;
        }
        stdext::checked_array_iterator<enum CDPComActivityType *>::checked_array_iterator<enum CDPComActivityType *>(
          &v35,
          v34,
          (unsigned __int8)v38);
        std::transform_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_enum_CDPActivityType______stdext::checked_array_iterator_enum_CDPComActivityType_____lambda_8923ed647b8b46339ca8930b08b3a710___(
          v36,
          v31[0],
          v31[1],
          &v35);
        *a3 = v28;
        if ( v31[0] )
          std::_Deallocate<16>(v31[0], (v32 - (unsigned __int64)v31[0]) & 0xFFFFFFFFFFFFFFFCuLL);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v33);
        return 0;
      }
      if ( (unsigned __int64)++v13 >= 2 || v18 != -2147221235 )
      {
        v29 = v18;
        v30 = 82;
        Log<long &,char const (&)[28],int>(
          v20,
          v19,
          (unsigned int)&v29,
          (unsigned int)".\\cdpcomafsusersettings.cpp",
          (__int64)&v30);
        if ( v31[0] )
        {
          std::_Deallocate<16>(v31[0], (v32 - (unsigned __int64)v31[0]) & 0xFFFFFFFFFFFFFFFCuLL);
          *(_OWORD *)v31 = 0;
          v32 = 0;
        }
        goto LABEL_36;
      }
      if ( v31[0] )
        std::_Deallocate<16>(v31[0], (v32 - (unsigned __int64)v31[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (unsigned int)".\\cdpcomafsusersettings.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180008fa0  mov     [rsp+arg_0], rbx
0x180008fa5  mov     [rsp+arg_10], rsi
0x180008faa  push    rdi
0x180008fab  push    r14
0x180008fad  push    r15
0x180008faf  sub     rsp, 0A0h
0x180008fb6  mov     r14, r9
0x180008fb9  mov     r15, r8
0x180008fbc  mov     rbx, rdx
0x180008fbf  test    rdx, rdx
0x180008fc2  jnz     short loc_180008FFA
0x180008fc4  mov     [rsp+0B8h+var_88], 2Eh ; '.'
0x180008fcc  mov     [rsp+0B8h+arg_8], 80070057h
0x180008fd7  lea     rax, [rsp+0B8h+var_88]
0x180008fdc  mov     [rsp+0B8h+var_98], rax
0x180008fe1  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x180008fe8  lea     r8, [rsp+0B8h+arg_8]
0x180008ff0  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180008ff5  jmp     loc_180009346
0x180008ffa  test    r15, r15
0x180008ffd  jnz     short loc_180009014
0x180008fff  mov     [rsp+0B8h+arg_8], 80004003h
0x18000900a  mov     [rsp+0B8h+var_88], 2Fh ; '/'
0x180009012  jmp     short loc_180008FD7
0x180009014  test    r14, r14
0x180009017  jnz     short loc_180009023
0x180009019  mov     [rsp+0B8h+var_88], 30h ; '0'
0x180009021  jmp     short loc_180008FCC
0x180009023  mov     [rsp+0B8h+var_68], 0
0x18000902c  lea     rcx, [rsp+0B8h+var_68]
0x180009031  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180009036  lea     rdx, [rsp+0B8h+var_68]
0x18000903b  mov     rcx, rbx
0x18000903e  call    cs:__imp_CDPCreateAFSUserSettingsInternal
0x180009044  test    eax, eax
0x180009046  jns     short loc_180009099
0x180009048  mov     [rsp+0B8h+var_88], eax
0x18000904c  mov     [rsp+0B8h+var_84], 35h ; '5'
0x180009054  lea     rax, [rsp+0B8h+var_84]
0x180009059  mov     [rsp+0B8h+var_98], rax
0x18000905e  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x180009065  lea     r8, [rsp+0B8h+var_88]
0x18000906a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18000906f  nop
0x180009070  mov     rcx, [rsp+0B8h+var_68]
0x180009075  test    rcx, rcx
0x180009078  jz      short loc_180009090
0x18000907a  mov     [rsp+0B8h+var_68], 0
0x180009083  mov     rdx, [rcx]
0x180009086  mov     rax, [rdx+10h]
0x18000908a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000908f  nop
0x180009090  mov     eax, [rsp+0B8h+var_88]
0x180009094  jmp     loc_18000934D
0x180009099  mov     byte ptr [rsp+0B8h+arg_8], 11h
0x1800090a1  xor     edi, edi
0x1800090a3  lea     rcx, [rsp+0B8h+var_80]
0x1800090a8  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x1800090ad  nop
0x1800090ae  movzx   ebx, byte ptr [rsp+0B8h+arg_8]
0x1800090b6  mov     rdx, [rsp+0B8h+var_80]
0x1800090bb  mov     rsi, [rsp+0B8h+var_80+8]
0x1800090c0  mov     rcx, rsi
0x1800090c3  sub     rcx, rdx
0x1800090c6  sar     rcx, 2
0x1800090ca  cmp     rbx, rcx
0x1800090cd  jnb     short loc_1800090D5
0x1800090cf  lea     rax, [rdx+rbx*4]
0x1800090d3  jmp     short loc_18000910F
0x1800090d5  jbe     short loc_180009114
0x1800090d7  mov     rax, [rsp+0B8h+var_70]
0x1800090dc  sub     rax, rdx
0x1800090df  sar     rax, 2
0x1800090e3  cmp     rbx, rax
0x1800090e6  jbe     short loc_1800090F7
0x1800090e8  mov     rdx, rbx
0x1800090eb  lea     rcx, [rsp+0B8h+var_80]
0x1800090f0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@W4CDPActivityType@@V?$allocator@W4CDPActivityType@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CDPActivityType>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800090f5  jmp     short loc_180009114
0x1800090f7  sub     rbx, rcx
0x1800090fa  shl     rbx, 2
0x1800090fe  mov     r8, rbx; Size
0x180009101  xor     edx, edx; Val
0x180009103  mov     rcx, rsi; void *
0x180009106  call    memset_0
0x18000910b  lea     rax, [rbx+rsi]
0x18000910f  mov     [rsp+0B8h+var_80+8], rax
0x180009114  mov     rcx, [rsp+0B8h+var_68]
0x180009119  mov     rax, [rcx]
0x18000911c  lea     r8, [rsp+0B8h+arg_8]
0x180009124  mov     rdx, [rsp+0B8h+var_80]
0x180009129  mov     rax, [rax+20h]
0x18000912d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009132  test    eax, eax
0x180009134  js      loc_1800092AD
0x18000913a  movzx   edx, byte ptr [rsp+0B8h+arg_8]
0x180009142  mov     ebx, edx
0x180009144  mov     r8, [rsp+0B8h+var_80]
0x180009149  mov     rdi, [rsp+0B8h+var_80+8]
0x18000914e  mov     rcx, rdi
0x180009151  sub     rcx, r8
0x180009154  sar     rcx, 2
0x180009158  cmp     rdx, rcx
0x18000915b  jnb     short loc_180009163
0x18000915d  lea     rax, [r8+rdx*4]
0x180009161  jmp     short loc_1800091A8
0x180009163  jbe     short loc_1800091AD
0x180009165  mov     rax, [rsp+0B8h+var_70]
0x18000916a  sub     rax, r8
0x18000916d  sar     rax, 2
0x180009171  cmp     rbx, rax
0x180009174  jbe     short loc_180009189
0x180009176  lea     rcx, [rsp+0B8h+var_80]
0x18000917b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@W4CDPActivityType@@V?$allocator@W4CDPActivityType@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CDPActivityType>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180009180  mov     dl, byte ptr [rsp+0B8h+arg_8]
0x180009187  jmp     short loc_1800091AD
0x180009189  sub     rbx, rcx
0x18000918c  shl     rbx, 2
0x180009190  mov     r8, rbx; Size
0x180009193  xor     edx, edx; Val
0x180009195  mov     rcx, rdi; void *
0x180009198  call    memset_0
0x18000919d  lea     rax, [rbx+rdi]
0x1800091a1  mov     dl, byte ptr [rsp+0B8h+arg_8]
0x1800091a8  mov     [rsp+0B8h+var_80+8], rax
0x1800091ad  mov     [r14], dl
0x1800091b0  movzx   edx, dl
0x1800091b3  lea     rcx, [rsp+0B8h+var_60]
0x1800091b8  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@W4CDPComActivityType@@@wil@@YA?AV?$unique_ptr@$$BY0A@W4CDPComActivityType@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<CDPComActivityType [0]>(unsigned __int64)
0x1800091bd  nop
0x1800091be  mov     rbx, [rsp+0B8h+var_60]
0x1800091c3  test    rbx, rbx
0x1800091c6  jz      short loc_180009241
0x1800091c8  movzx   r8d, byte ptr [rsp+0B8h+arg_8]
0x1800091d1  mov     rdx, rbx
0x1800091d4  lea     rcx, [rsp+0B8h+var_58]
0x1800091d9  call    ??0?$checked_array_iterator@PEAW4CDPComActivityType@@@stdext@@QEAA@QEAW4CDPComActivityType@@_K1@Z; stdext::checked_array_iterator<CDPComActivityType *>::checked_array_iterator<CDPComActivityType *>(CDPComActivityType * const,unsigned __int64,unsigned __int64)
0x1800091de  movups  xmm0, [rsp+0B8h+var_58]
0x1800091e3  movsd   xmm1, [rsp+0B8h+var_48]
0x1800091e9  movaps  [rsp+0B8h+var_58], xmm0
0x1800091ee  movsd   [rsp+0B8h+var_48], xmm1
0x1800091f4  lea     r9, [rsp+0B8h+var_58]
0x1800091f9  mov     r8, [rsp+0B8h+var_80+8]
0x1800091fe  mov     rdx, [rsp+0B8h+var_80]
0x180009203  lea     rcx, [rsp+0B8h+var_38]
0x18000920b  call    std__transform_std___Vector_iterator_std___Vector_val_std___Simple_types_enum_CDPActivityType______stdext__checked_array_iterator_enum_CDPComActivityType_____lambda_8923ed647b8b46339ca8930b08b3a710___
0x180009210  mov     [r15], rbx
0x180009213  mov     rcx, [rsp+0B8h+var_80]
0x180009218  test    rcx, rcx
0x18000921b  jz      short loc_18000922F
0x18000921d  mov     rdx, [rsp+0B8h+var_70]
0x180009222  sub     rdx, rcx
0x180009225  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180009229  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000922e  nop
0x18000922f  lea     rcx, [rsp+0B8h+var_68]
0x180009234  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180009239  nop
0x18000923a  xor     eax, eax
0x18000923c  jmp     loc_18000934D
0x180009241  mov     [rsp+0B8h+var_88], 8007000Eh
0x180009249  mov     [rsp+0B8h+var_84], 45h ; 'E'
0x180009251  lea     rax, [rsp+0B8h+var_84]
0x180009256  mov     [rsp+0B8h+var_98], rax
0x18000925b  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x180009262  lea     r8, [rsp+0B8h+var_88]
0x180009267  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18000926c  nop
0x18000926d  mov     rcx, [rsp+0B8h+var_80]
0x180009272  test    rcx, rcx
0x180009275  jz      short loc_18000929A
0x180009277  mov     rdx, [rsp+0B8h+var_70]
0x18000927c  sub     rdx, rcx
0x18000927f  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180009283  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009288  xorps   xmm0, xmm0
0x18000928b  movdqu  xmmword ptr [rsp+0B8h+var_80], xmm0
0x180009291  mov     [rsp+0B8h+var_70], 0
0x18000929a  lea     rcx, [rsp+0B8h+var_68]
0x18000929f  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800092a4  mov     eax, [rsp+0B8h+var_88]
0x1800092a8  jmp     loc_18000934D
0x1800092ad  inc     rdi
0x1800092b0  cmp     rdi, 2
0x1800092b4  jnb     short loc_1800092E1
0x1800092b6  cmp     eax, 8004010Dh
0x1800092bb  jnz     short loc_1800092E1
0x1800092bd  mov     rcx, [rsp+0B8h+var_80]
0x1800092c2  test    rcx, rcx
0x1800092c5  jz      loc_1800090A3
0x1800092cb  mov     rdx, [rsp+0B8h+var_70]
0x1800092d0  sub     rdx, rcx
0x1800092d3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800092d7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800092dc  jmp     loc_1800090A3
0x1800092e1  mov     [rsp+0B8h+var_88], eax
0x1800092e5  mov     [rsp+0B8h+var_84], 52h ; 'R'
0x1800092ed  lea     rax, [rsp+0B8h+var_84]
0x1800092f2  mov     [rsp+0B8h+var_98], rax
0x1800092f7  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x1800092fe  lea     r8, [rsp+0B8h+var_88]
0x180009303  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x180009308  nop
0x180009309  mov     rcx, [rsp+0B8h+var_80]
0x18000930e  test    rcx, rcx
0x180009311  jz      short loc_180009336
0x180009313  mov     rdx, [rsp+0B8h+var_70]
0x180009318  sub     rdx, rcx
0x18000931b  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000931f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009324  xorps   xmm0, xmm0
0x180009327  movdqu  xmmword ptr [rsp+0B8h+var_80], xmm0
0x18000932d  mov     [rsp+0B8h+var_70], 0
0x180009336  lea     rcx, [rsp+0B8h+var_68]
0x18000933b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180009340  mov     eax, [rsp+0B8h+var_88]
0x180009344  jmp     short loc_18000934D
0x180009346  mov     eax, [rsp+0B8h+arg_8]
0x18000934d  lea     r11, [rsp+0B8h+var_18]
0x180009355  mov     rbx, [r11+20h]
0x180009359  mov     rsi, [r11+30h]
0x18000935d  mov     rsp, r11
0x180009360  pop     r15
0x180009362  pop     r14
0x180009364  pop     rdi
0x180009365  retn
```
