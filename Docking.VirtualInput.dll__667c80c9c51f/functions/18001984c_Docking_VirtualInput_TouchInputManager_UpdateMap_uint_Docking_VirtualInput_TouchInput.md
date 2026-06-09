# Docking::VirtualInput::TouchInputManager::_UpdateMap(uint,Docking::VirtualInput::TouchInput *)

- ea: `0x18001984c`
- end: `0x180019a9c`
- name: `?_UpdateMap@TouchInputManager@VirtualInput@Docking@@AEAAJIPEAUTouchInput@23@@Z`
- size: `592`
- prototype: `__int64 __fastcall(Docking::VirtualInput::TouchInputManager *__hidden this, unsigned int, struct Docking::VirtualInput::TouchInput *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800174bc`

## callees

- `0x1800036a0`
- `0x180004ba0`
- `0x180004bac`
- `0x1800067a4`
- `0x180015580`
- `0x180016e9c`
- `0x180016f20`
- `0x18001984c`
- `0x180019d78`
- `0x180019e08`
- `0x180019e78`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::TouchInputManager::_UpdateMap(
        Docking::VirtualInput::TouchInputManager *this,
        unsigned int a2,
        struct Docking::VirtualInput::TouchInput *a3)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // [rsp+20h] [rbp-A8h]
  unsigned int i; // [rsp+24h] [rbp-A4h]
  char *v12; // [rsp+28h] [rbp-A0h]
  _BYTE v13[8]; // [rsp+30h] [rbp-98h] BYREF
  int v14; // [rsp+38h] [rbp-90h]
  char *v15; // [rsp+40h] [rbp-88h]
  char *v16; // [rsp+48h] [rbp-80h]
  char *v17; // [rsp+50h] [rbp-78h]
  _BYTE v18[8]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v19[20]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v20[16]; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v21[24]; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  for ( i = 0; i < a2; ++i )
  {
    v12 = (char *)a3 + 20 * i;
    HIBYTE(v10) = v12[12];
    BYTE2(v10) = v12[13];
    if ( !HIBYTE(v10) || BYTE2(v10) )
    {
      if ( BYTE2(v10) )
      {
        v16 = (char *)this + 8;
        std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::find(
          (char *)this + 8,
          v13,
          v12 + 8);
        v17 = (char *)this + 8;
        v8 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::end(
               (char *)this + 8,
               v18);
        if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(
                                v13,
                                v8) )
        {
          qmemcpy(v19, v12, sizeof(v19));
          v9 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator->(v13);
          qmemcpy((void *)(v9 + 4), v19, 0x14u);
        }
      }
    }
    else
    {
      v3 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::size((char *)this + 8);
      v4 = *((unsigned int *)this + 19);
      LOBYTE(v10) = v3 < v4;
      LOBYTE(v4) = v3 < v4;
      BYTE1(v10) = (unsigned __int8)wil::verify_bool<bool,0>(v4) == 0;
      LOBYTE(v5) = BYTE1(v10);
      if ( (unsigned __int8)wil::verify_bool<bool,0>(v5) )
      {
        v14 = wil::verify_BOOL<int>(2147483659LL);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\touchinputmanager.cpp",
          (const char *)0x8000000BLL,
          v10);
        return 2147483659LL;
      }
      v15 = (char *)this + 8;
      v7 = std::pair<int const,Docking::VirtualInput::TouchInput>::pair<int const,Docking::VirtualInput::TouchInput>(
             v21,
             v12 + 8,
             v12);
      std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::insert(
        v15,
        v20,
        v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001984c  mov     [rsp+arg_10], r8
0x180019851  mov     [rsp+arg_8], edx
0x180019855  mov     [rsp+arg_0], rcx
0x18001985a  push    rsi
0x18001985b  push    rdi
0x18001985c  sub     rsp, 0B8h
0x180019863  mov     rax, cs:__security_cookie
0x18001986a  xor     rax, rsp
0x18001986d  mov     [rsp+0C8h+var_28], rax
0x180019875  mov     [rsp+0C8h+var_A4], 0
0x18001987d  jmp     short loc_180019889
0x18001987f  mov     eax, [rsp+0C8h+var_A4]
0x180019883  inc     eax
0x180019885  mov     [rsp+0C8h+var_A4], eax
0x180019889  mov     eax, [rsp+0C8h+arg_8]
0x180019890  cmp     [rsp+0C8h+var_A4], eax
0x180019894  jnb     loc_180019A80
0x18001989a  mov     eax, [rsp+0C8h+var_A4]
0x18001989e  imul    rax, 14h
0x1800198a2  mov     rcx, [rsp+0C8h+arg_10]
0x1800198aa  add     rcx, rax
0x1800198ad  mov     rax, rcx
0x1800198b0  mov     [rsp+0C8h+var_A0], rax
0x1800198b5  mov     rax, [rsp+0C8h+var_A0]
0x1800198ba  mov     al, [rax+0Ch]
0x1800198bd  mov     byte ptr [rsp+0C8h+var_A8+3], al
0x1800198c1  mov     rax, [rsp+0C8h+var_A0]
0x1800198c6  mov     al, [rax+0Dh]
0x1800198c9  mov     byte ptr [rsp+0C8h+var_A8+2], al
0x1800198cd  movzx   eax, byte ptr [rsp+0C8h+var_A8+3]
0x1800198d2  test    eax, eax
0x1800198d4  jz      loc_1800199DC
0x1800198da  movzx   eax, byte ptr [rsp+0C8h+var_A8+2]
0x1800198df  test    eax, eax
0x1800198e1  jnz     loc_1800199DC
0x1800198e7  mov     rax, [rsp+0C8h+arg_0]
0x1800198ef  add     rax, 8
0x1800198f3  mov     rcx, rax
0x1800198f6  call    ?size@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::size(void)
0x1800198fb  mov     rcx, [rsp+0C8h+arg_0]
0x180019903  mov     ecx, [rcx+4Ch]
0x180019906  cmp     rax, rcx
0x180019909  jnb     short loc_180019912
0x18001990b  mov     byte ptr [rsp+0C8h+var_A8], 1
0x180019910  jmp     short loc_180019917
0x180019912  mov     byte ptr [rsp+0C8h+var_A8], 0; int
0x180019917  mov     cl, byte ptr [rsp+0C8h+var_A8]
0x18001991b  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x180019920  movzx   eax, al
0x180019923  test    eax, eax
0x180019925  jnz     short loc_18001992E
0x180019927  mov     byte ptr [rsp+0C8h+var_A8+1], 1
0x18001992c  jmp     short loc_180019933
0x18001992e  mov     byte ptr [rsp+0C8h+var_A8+1], 0
0x180019933  mov     cl, byte ptr [rsp+0C8h+var_A8+1]
0x180019937  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x18001993c  movzx   eax, al
0x18001993f  test    eax, eax
0x180019941  jz      short loc_18001998B
0x180019943  mov     ecx, 8000000Bh
0x180019948  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x18001994d  mov     [rsp+0C8h+var_90], eax
0x180019951  xor     eax, eax
0x180019953  cmp     eax, 1
0x180019956  jz      short loc_18001997B
0x180019958  mov     rax, [rsp+0C8h]
0x180019960  mov     r9d, 8000000Bh; char *
0x180019966  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\docking\\virtualinpu"...
0x18001996d  mov     edx, 91h; void *
0x180019972  mov     rcx, rax; this
0x180019975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001997a  nop
0x18001997b  mov     eax, 8000000Bh
0x180019980  jmp     loc_180019A82
0x180019985  xor     eax, eax
0x180019987  test    eax, eax
0x180019989  jnz     short loc_180019943
0x18001998b  xor     eax, eax
0x18001998d  test    eax, eax
0x18001998f  jnz     loc_1800198E7
0x180019995  mov     rax, [rsp+0C8h+arg_0]
0x18001999d  add     rax, 8
0x1800199a1  mov     [rsp+0C8h+var_88], rax
0x1800199a6  mov     rax, [rsp+0C8h+var_A0]
0x1800199ab  add     rax, 8
0x1800199af  mov     r8, [rsp+0C8h+var_A0]
0x1800199b4  mov     rdx, rax
0x1800199b7  lea     rcx, [rsp+0C8h+var_40]
0x1800199bf  call    ??$?0AEAHAEAUTouchInput@VirtualInput@Docking@@$0A@@?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@QEAA@AEAHAEAUTouchInput@VirtualInput@Docking@@@Z; std::pair<int const,Docking::VirtualInput::TouchInput>::pair<int const,Docking::VirtualInput::TouchInput>(int &,Docking::VirtualInput::TouchInput &)
0x1800199c4  mov     r8, rax
0x1800199c7  lea     rdx, [rsp+0C8h+var_50]
0x1800199cc  mov     rcx, [rsp+0C8h+var_88]
0x1800199d1  call    ?insert@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@2@@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::insert(std::pair<int const,Docking::VirtualInput::TouchInput> &&)
0x1800199d6  nop
0x1800199d7  jmp     loc_180019A7B
0x1800199dc  movzx   eax, byte ptr [rsp+0C8h+var_A8+2]
0x1800199e1  test    eax, eax
0x1800199e3  jz      loc_180019A7B
0x1800199e9  mov     rax, [rsp+0C8h+arg_0]
0x1800199f1  add     rax, 8
0x1800199f5  mov     [rsp+0C8h+var_80], rax
0x1800199fa  mov     rax, [rsp+0C8h+var_A0]
0x1800199ff  add     rax, 8
0x180019a03  mov     r8, rax
0x180019a06  lea     rdx, [rsp+0C8h+var_98]
0x180019a0b  mov     rcx, [rsp+0C8h+var_80]
0x180019a10  call    ?find@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@AEBH@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::find(int const &)
0x180019a15  nop
0x180019a16  mov     rax, [rsp+0C8h+arg_0]
0x180019a1e  add     rax, 8
0x180019a22  mov     [rsp+0C8h+var_78], rax
0x180019a27  lea     rdx, [rsp+0C8h+var_70]
0x180019a2c  mov     rcx, [rsp+0C8h+var_78]
0x180019a31  call    ?end@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::end(void)
0x180019a36  mov     rdx, rax
0x180019a39  lea     rcx, [rsp+0C8h+var_98]
0x180019a3e  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180019a43  movzx   eax, al
0x180019a46  test    eax, eax
0x180019a48  jz      short loc_180019A7B
0x180019a4a  lea     rax, [rsp+0C8h+var_68]
0x180019a4f  mov     rdi, rax
0x180019a52  mov     rsi, [rsp+0C8h+var_A0]
0x180019a57  mov     ecx, 14h
0x180019a5c  rep movsb
0x180019a5e  lea     rcx, [rsp+0C8h+var_98]
0x180019a63  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>::operator->(void)
0x180019a68  lea     rcx, [rsp+0C8h+var_68]
0x180019a6d  lea     rdi, [rax+4]
0x180019a71  mov     rsi, rcx
0x180019a74  mov     ecx, 14h
0x180019a79  rep movsb
0x180019a7b  jmp     loc_18001987F
0x180019a80  xor     eax, eax
0x180019a82  mov     rcx, [rsp+0C8h+var_28]
0x180019a8a  xor     rcx, rsp; StackCookie
0x180019a8d  call    __security_check_cookie
0x180019a92  add     rsp, 0B8h
0x180019a99  pop     rdi
0x180019a9a  pop     rsi
0x180019a9b  retn
```
