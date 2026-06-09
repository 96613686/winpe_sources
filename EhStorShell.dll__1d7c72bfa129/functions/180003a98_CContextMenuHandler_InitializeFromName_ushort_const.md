# CContextMenuHandler::InitializeFromName(ushort const *)

- ea: `0x180003a98`
- end: `0x180003c8c`
- name: `?InitializeFromName@CContextMenuHandler@@QEAAJPEBG@Z`
- size: `500`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, const unsigned __int16 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003670`
- `0x1800048e0`

## callees

- `0x180003a98`
- `0x1800064cc`
- `0x18000684c`
- `0x180009b6c`
- `0x18000a3a8`
- `0x18000c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003b13`
- `ole32!CoCreateInstance` at `0x180003b13`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::InitializeFromName(
        CContextMenuHandler *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  HRESULT v6; // eax
  unsigned int SiloActionList; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // r14
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+88h] [rbp+48h] BYREF

  v16 = 0;
  ppv = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
  v6 = CoCreateInstance(&CLSID_EnumEnhancedStorageACT, 0, 1u, &GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7, &ppv);
  SiloActionList = v6;
  if ( v6 >= 0 )
  {
    v10 = (_QWORD *)((char *)this + 24);
    v11 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, char *))(*(_QWORD *)ppv + 32LL))(
            ppv,
            a2,
            (char *)this + 24);
    SiloActionList = v11;
    if ( v11 >= 0 )
    {
      if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v10)(
             *v10,
             &GUID_022150a1_113d_11df_bb61_001aa01bbc58,
             &v13) < 0
        || (v15 = 1, (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 104LL))(v13, &v15) < 0)
        || v15 )
      {
        *((_DWORD *)this + 16) = 1;
        v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v10 + 40LL))(*v10, &v16);
        SiloActionList = v6;
        if ( v6 >= 0 )
        {
          *((_DWORD *)this + 17) = v16 == 1;
          SiloActionList = CContextMenuHandler::CreateSiloActionList(this);
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v9 = 19;
            goto LABEL_8;
          }
        }
      }
      else
      {
        SiloActionList = -2147467259;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids,
        v11,
        (__int64)a2);
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = 17;
LABEL_8:
      WPP_SF_d(v8[2], v9, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, (unsigned int)v6);
    }
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return SiloActionList;
}

```

## disassembly

```asm
0x180003a98  mov     [rsp-28h+arg_0], rbx
0x180003a9d  push    rbp
0x180003a9e  push    rsi
0x180003a9f  push    rdi
0x180003aa0  push    r12
0x180003aa2  push    r14
0x180003aa4  mov     rbp, rsp
0x180003aa7  sub     rsp, 40h
0x180003aab  mov     rsi, rdx
0x180003aae  mov     rdi, rcx
0x180003ab1  mov     [rbp+arg_18], 0
0x180003ab8  mov     [rbp+var_8], 0
0x180003ac0  mov     [rbp+var_10], 0
0x180003ac8  lea     r12, WPP_GLOBAL_Control
0x180003acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ad6  cmp     rcx, r12
0x180003ad9  jz      short loc_180003AF6
0x180003adb  test    byte ptr [rcx+1Ch], 20h
0x180003adf  jz      short loc_180003AF6
0x180003ae1  mov     edx, 10h
0x180003ae6  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180003aed  mov     rcx, [rcx+10h]
0x180003af1  call    WPP_SF_
0x180003af6  lea     rax, [rbp+var_8]
0x180003afa  mov     [rsp+40h+ppv], rax; ppv
0x180003aff  lea     r9, _GUID_09b224bd_1335_4631_a7ff_cfd3a92646d7; riid
0x180003b06  xor     edx, edx; pUnkOuter
0x180003b08  lea     r8d, [rdx+1]; dwClsContext
0x180003b0c  lea     rcx, CLSID_EnumEnhancedStorageACT; rclsid
0x180003b13  call    cs:__imp_CoCreateInstance
0x180003b19  mov     ebx, eax
0x180003b1b  test    eax, eax
0x180003b1d  jns     short loc_180003B56
0x180003b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b26  cmp     rcx, r12
0x180003b29  jz      loc_180003C4D
0x180003b2f  test    byte ptr [rcx+1Ch], 2
0x180003b33  jz      loc_180003C4D
0x180003b39  mov     edx, 11h
0x180003b3e  mov     r9d, eax
0x180003b41  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180003b48  mov     rcx, [rcx+10h]
0x180003b4c  call    WPP_SF_d
0x180003b51  jmp     loc_180003C4D
0x180003b56  mov     rcx, [rbp+var_8]
0x180003b5a  lea     r14, [rdi+18h]
0x180003b5e  mov     rax, [rcx]
0x180003b61  mov     r8, r14
0x180003b64  mov     rdx, rsi
0x180003b67  mov     rax, [rax+20h]
0x180003b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b70  mov     ebx, eax
0x180003b72  test    eax, eax
0x180003b74  jns     short loc_180003BB2
0x180003b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b7d  cmp     rcx, r12
0x180003b80  jz      loc_180003C4D
0x180003b86  test    byte ptr [rcx+1Ch], 2
0x180003b8a  jz      loc_180003C4D
0x180003b90  mov     edx, 12h
0x180003b95  mov     [rsp+40h+ppv], rsi
0x180003b9a  mov     r9d, eax
0x180003b9d  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x180003ba4  mov     rcx, [rcx+10h]
0x180003ba8  call    WPP_SF_DS
0x180003bad  jmp     loc_180003C4D
0x180003bb2  mov     rcx, [r14]
0x180003bb5  mov     rax, [rcx]
0x180003bb8  lea     r8, [rbp+var_10]
0x180003bbc  lea     rdx, _GUID_022150a1_113d_11df_bb61_001aa01bbc58
0x180003bc3  mov     rax, [rax]
0x180003bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcb  test    eax, eax
0x180003bcd  js      short loc_180003BFB
0x180003bcf  mov     [rbp+arg_10], 1
0x180003bd6  mov     rcx, [rbp+var_10]
0x180003bda  mov     rax, [rcx]
0x180003bdd  lea     rdx, [rbp+arg_10]
0x180003be1  mov     rax, [rax+68h]
0x180003be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bea  test    eax, eax
0x180003bec  js      short loc_180003BFB
0x180003bee  cmp     [rbp+arg_10], 0
0x180003bf2  jnz     short loc_180003BFB
0x180003bf4  mov     ebx, 80004005h
0x180003bf9  jmp     short loc_180003C4D
0x180003bfb  mov     dword ptr [rdi+40h], 1
0x180003c02  mov     rcx, [r14]
0x180003c05  mov     rax, [rcx]
0x180003c08  lea     rdx, [rbp+arg_18]
0x180003c0c  mov     rax, [rax+28h]
0x180003c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c15  mov     ebx, eax
0x180003c17  test    eax, eax
0x180003c19  jns     short loc_180003C37
0x180003c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c22  cmp     rcx, r12
0x180003c25  jz      short loc_180003C4D
0x180003c27  test    byte ptr [rcx+1Ch], 2
0x180003c2b  jz      short loc_180003C4D
0x180003c2d  mov     edx, 13h
0x180003c32  jmp     loc_180003B3E
0x180003c37  xor     eax, eax
0x180003c39  cmp     [rbp+arg_18], 1
0x180003c3d  setz    al
0x180003c40  mov     [rdi+44h], eax
0x180003c43  mov     rcx, rdi; this
0x180003c46  call    ?CreateSiloActionList@CContextMenuHandler@@QEAAJXZ; CContextMenuHandler::CreateSiloActionList(void)
0x180003c4b  mov     ebx, eax
0x180003c4d  mov     rcx, [rbp+var_10]
0x180003c51  test    rcx, rcx
0x180003c54  jz      short loc_180003C63
0x180003c56  mov     rax, [rcx]
0x180003c59  mov     rax, [rax+10h]
0x180003c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c62  nop
0x180003c63  mov     rcx, [rbp+var_8]
0x180003c67  test    rcx, rcx
0x180003c6a  jz      short loc_180003C79
0x180003c6c  mov     rax, [rcx]
0x180003c6f  mov     rax, [rax+10h]
0x180003c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c78  nop
0x180003c79  mov     eax, ebx
0x180003c7b  mov     rbx, [rsp+40h+arg_0]
0x180003c80  add     rsp, 40h
0x180003c84  pop     r14
0x180003c86  pop     r12
0x180003c88  pop     rdi
0x180003c89  pop     rsi
0x180003c8a  pop     rbp
0x180003c8b  retn
```
