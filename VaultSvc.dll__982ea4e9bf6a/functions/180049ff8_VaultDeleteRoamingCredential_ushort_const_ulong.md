# VaultDeleteRoamingCredential(ushort const *,ulong)

- ea: `0x180049ff8`
- end: `0x18004a1da`
- name: `?VaultDeleteRoamingCredential@@YAKPEBGK@Z`
- size: `482`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800483f0`

## callees

- `0x1800010b4`
- `0x180003140`
- `0x18000e148`
- `0x180012210`
- `0x18003577c`
- `0x18003b7d8`
- `0x180049ff8`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VaultDeleteRoamingCredential(const unsigned __int16 *a1)
{
  unsigned int RoamingCredential; // eax
  _BYTE *v3; // rdx
  unsigned int v4; // ebx
  HLOCAL v5; // rcx
  __int64 v6; // rax
  _BYTE *v8; // rbx
  unsigned int v9; // esi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  _BYTE *v14; // rcx
  HLOCAL v15; // rcx
  __int64 v16; // rax
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-28h]
  __int64 (__fastcall *v19)(_QWORD); // [rsp+48h] [rbp-20h] BYREF
  int v20[2]; // [rsp+50h] [rbp-18h] BYREF
  int v21; // [rsp+58h] [rbp-10h]
  const unsigned __int16 *v22; // [rsp+A0h] [rbp+38h] BYREF

  v19 = AutoDereference<IVaultKeyManager>;
  *(_QWORD *)v20 = 0;
  v21 = 0;
  hMem = 0;
  v18 = 0;
  RoamingCredential = GetRoamingCredential((int)a1, (int)v20, (int)&hMem, 0, (struct _GUID *)&Vault_DefaultVault_ID);
  v4 = RoamingCredential;
  if ( RoamingCredential == 1168 )
  {
    v15 = hMem;
    if ( hMem )
    {
      v16 = v18;
      if ( v18 )
      {
        v3 = hMem;
        do
        {
          *v3++ = 0;
          --v16;
        }
        while ( v16 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        ((void (__fastcall *)(HLOCAL, _BYTE *))AutoDereference<IVaultKeyManager>)(v15, v3);
      else
        VaultFreeInternal(v15);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v19);
    return 0;
  }
  else if ( RoamingCredential )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        138,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        RoamingCredential);
    v5 = hMem;
    if ( hMem )
    {
      v6 = v18;
      if ( v18 )
      {
        v3 = hMem;
        do
        {
          *v3++ = 0;
          --v6;
        }
        while ( v6 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        ((void (__fastcall *)(HLOCAL, _BYTE *))AutoDereference<IVaultKeyManager>)(v5, v3);
      else
        VaultFreeInternal(v5);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v19);
    return v4;
  }
  else
  {
    v8 = hMem;
    v9 = (*(__int64 (__fastcall **)(HLOCAL, const unsigned __int16 *))(*(_QWORD *)hMem + 160LL))(hMem, a1);
    if ( !v9 && (unsigned int)dword_18005F0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005F0C0) )
    {
      v22 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)&byte_180054C7F,
        v11,
        v12,
        (__int64)&v22);
    }
    if ( v8 )
    {
      v13 = v18;
      if ( v18 )
      {
        v14 = v8;
        do
        {
          *v14++ = 0;
          --v13;
        }
        while ( v13 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        AutoDereference<IVaultKeyManager>(v8);
      else
        VaultFreeInternal(v8);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v19);
    return v9;
  }
}

```

## disassembly

```asm
0x180049ff8  push    rbp
0x180049ffa  push    rbx
0x180049ffb  push    rsi
0x180049ffc  push    rdi
0x180049ffd  mov     rbp, rsp
0x18004a000  sub     rsp, 68h
0x18004a004  mov     rdi, rcx
0x18004a007  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18004a00e  mov     [rbp+var_20], rax
0x18004a012  mov     qword ptr [rbp+var_18], 0
0x18004a01a  mov     [rbp+var_10], 0
0x18004a021  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18004a028  mov     [rbp+var_38], rax
0x18004a02c  mov     [rbp+hMem], 0
0x18004a034  mov     [rbp+var_28], 0
0x18004a03b  lea     rax, Vault_DefaultVault_ID
0x18004a042  mov     [rsp+68h+var_48], rax; struct _GUID *
0x18004a047  xor     r9d, r9d; int
0x18004a04a  lea     r8, [rbp+hMem]; int
0x18004a04e  lea     rdx, [rbp+var_18]; int
0x18004a052  call    GetRoamingCredential
0x18004a057  mov     ebx, eax
0x18004a059  cmp     eax, 490h
0x18004a05e  jz      loc_18004A186
0x18004a064  test    eax, eax
0x18004a066  jz      loc_18004A0EE
0x18004a06c  lea     rax, WPP_GLOBAL_Control
0x18004a073  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a07a  cmp     rcx, rax
0x18004a07d  jz      short loc_18004A09E
0x18004a07f  test    byte ptr [rcx+1Ch], 2
0x18004a083  jz      short loc_18004A09E
0x18004a085  mov     edx, 8Ah
0x18004a08a  mov     r9d, ebx
0x18004a08d  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x18004a094  mov     rcx, [rcx+10h]
0x18004a098  call    WPP_SF_d
0x18004a09d  nop
0x18004a09e  mov     rcx, [rbp+hMem]; hMem
0x18004a0a2  test    rcx, rcx
0x18004a0a5  jz      short loc_18004A0DD
0x18004a0a7  mov     eax, [rbp+var_28]
0x18004a0aa  test    eax, eax
0x18004a0ac  jz      short loc_18004A0C7
0x18004a0ae  test    rcx, rcx
0x18004a0b1  jz      short loc_18004A0C7
0x18004a0b3  test    rax, rax
0x18004a0b6  jz      short loc_18004A0C7
0x18004a0b8  mov     rdx, rcx
0x18004a0bb  mov     byte ptr [rdx], 0
0x18004a0be  inc     rdx
0x18004a0c1  sub     rax, 1
0x18004a0c5  jnz     short loc_18004A0BB
0x18004a0c7  mov     rax, [rbp+var_38]
0x18004a0cb  test    rax, rax
0x18004a0ce  jz      short loc_18004A0D7
0x18004a0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0d5  jmp     short loc_18004A0DD
0x18004a0d7  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18004a0dc  nop
0x18004a0dd  lea     rcx, [rbp+var_20]
0x18004a0e1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004a0e6  nop
0x18004a0e7  mov     eax, ebx
0x18004a0e9  jmp     loc_18004A1D1
0x18004a0ee  mov     rbx, [rbp+hMem]
0x18004a0f2  mov     rax, [rbx]
0x18004a0f5  mov     rdx, rdi
0x18004a0f8  mov     rcx, rbx
0x18004a0fb  mov     rax, [rax+0A0h]
0x18004a102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a107  mov     esi, eax
0x18004a109  test    eax, eax
0x18004a10b  jnz     short loc_18004A142
0x18004a10d  mov     ecx, cs:dword_18005F0C0
0x18004a113  cmp     ecx, 5
0x18004a116  jbe     short loc_18004A142
0x18004a118  lea     rcx, dword_18005F0C0
0x18004a11f  call    _tlgKeywordOn
0x18004a124  test    al, al
0x18004a126  jz      short loc_18004A142
0x18004a128  mov     [rbp+arg_10], rdi
0x18004a12c  lea     rax, [rbp+arg_10]
0x18004a130  mov     [rsp+68h+var_48], rax
0x18004a135  lea     rdx, byte_180054C7F
0x18004a13c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004a141  nop
0x18004a142  test    rbx, rbx
0x18004a145  jz      short loc_18004A178
0x18004a147  mov     eax, [rbp+var_28]
0x18004a14a  cmp     rax, 1
0x18004a14e  jb      short loc_18004A15F
0x18004a150  mov     rcx, rbx
0x18004a153  mov     byte ptr [rcx], 0
0x18004a156  inc     rcx
0x18004a159  sub     rax, 1
0x18004a15d  jnz     short loc_18004A153
0x18004a15f  mov     rax, [rbp+var_38]
0x18004a163  mov     rcx, rbx; hMem
0x18004a166  test    rax, rax
0x18004a169  jz      short loc_18004A172
0x18004a16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a170  jmp     short loc_18004A178
0x18004a172  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18004a177  nop
0x18004a178  lea     rcx, [rbp+var_20]
0x18004a17c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004a181  nop
0x18004a182  mov     eax, esi
0x18004a184  jmp     short loc_18004A1D1
0x18004a186  mov     rcx, [rbp+hMem]; hMem
0x18004a18a  test    rcx, rcx
0x18004a18d  jz      short loc_18004A1C5
0x18004a18f  mov     eax, [rbp+var_28]
0x18004a192  test    eax, eax
0x18004a194  jz      short loc_18004A1AF
0x18004a196  test    rcx, rcx
0x18004a199  jz      short loc_18004A1AF
0x18004a19b  test    rax, rax
0x18004a19e  jz      short loc_18004A1AF
0x18004a1a0  mov     rdx, rcx
0x18004a1a3  mov     byte ptr [rdx], 0
0x18004a1a6  inc     rdx
0x18004a1a9  sub     rax, 1
0x18004a1ad  jnz     short loc_18004A1A3
0x18004a1af  mov     rax, [rbp+var_38]
0x18004a1b3  test    rax, rax
0x18004a1b6  jz      short loc_18004A1BF
0x18004a1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1bd  jmp     short loc_18004A1C5
0x18004a1bf  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18004a1c4  nop
0x18004a1c5  lea     rcx, [rbp+var_20]
0x18004a1c9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004a1ce  nop
0x18004a1cf  xor     eax, eax
0x18004a1d1  add     rsp, 68h
0x18004a1d5  pop     rdi
0x18004a1d6  pop     rsi
0x18004a1d7  pop     rbx
0x18004a1d8  pop     rbp
0x18004a1d9  retn
```
