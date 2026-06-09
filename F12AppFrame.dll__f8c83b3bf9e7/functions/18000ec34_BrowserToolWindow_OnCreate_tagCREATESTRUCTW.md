# BrowserToolWindow::OnCreate(tagCREATESTRUCTW *)

- ea: `0x18000ec34`
- end: `0x18000ee86`
- name: `?OnCreate@BrowserToolWindow@@QEAAHPEAUtagCREATESTRUCTW@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(BrowserToolWindow *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f8b0`

## callees

- `0x18000c580`
- `0x18000c9e4`
- `0x18000ec34`
- `0x180011e34`
- `0x18003105c`
- `0x1800313c4`
- `0x180035010`

## import_xrefs

- `ole32!OleInitialize` at `0x18000ec5e`
- `ole32!OleInitialize` at `0x18000ec5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BrowserToolWindow::OnCreate(BrowserToolWindow *this, struct tagCREATESTRUCTW *a2)
{
  int v3; // esi
  struct tagCREATESTRUCTW *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // r14
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // esi
  struct tagCREATESTRUCTW *v15; // rax
  struct tagCREATESTRUCTW *v16; // rcx
  __int64 v17; // rcx
  struct tagCREATESTRUCTW *v19; // [rsp+58h] [rbp+38h] BYREF
  __int64 v20; // [rsp+60h] [rbp+40h] BYREF
  __int64 v21; // [rsp+68h] [rbp+48h]

  v19 = a2;
  if ( (unsigned int)AtlAxWinInit() )
  {
    OleInitialize(0);
    v19 = 0;
    v3 = ATL::CComObject<WPCHost>::CreateInstance(&v19);
    v4 = v19;
    if ( *((struct tagCREATESTRUCTW **)this + 17) != v19 )
    {
      if ( v19 )
        (*((void (__fastcall **)(struct tagCREATESTRUCTW *))v19->lpCreateParams + 1))(v19);
      v5 = *((_QWORD *)this + 17);
      *((_QWORD *)this + 17) = v4;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( !v3 )
    {
      v6 = 0;
      v21 = 0;
      v7 = *((_QWORD *)this + 17);
      v8 = ((unsigned __int64)this + 72) & -(__int64)(this != 0);
      if ( *(_QWORD *)(v7 + 96) != v8 )
      {
        if ( v8 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v8 + 8LL))(((unsigned __int64)this + 72) & -(__int64)(this != 0));
        v9 = *(_QWORD *)(v7 + 96);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        *(_QWORD *)(v7 + 96) = v8;
      }
      if ( !(unsigned int)WPCHost::CreateWebPlatformControl(v7, (__int64 *)this + 21) )
      {
        v10 = *(_QWORD *)(v7 + 104);
        if ( v10 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v7 + 104));
          v6 = v10;
          v21 = v10;
        }
        v11 = *((_QWORD *)this + 1);
        AtlAxWinInit();
        if ( v6 )
        {
          v19 = 0;
          v14 = ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(v13, v12, &v19);
          if ( v14 >= 0 )
          {
            v20 = 0;
            v14 = (*(__int64 (__fastcall **)(struct tagCREATESTRUCTW *, GUID *, __int64 *))v19->lpCreateParams)(
                    v19,
                    &GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e,
                    &v20);
            if ( v14 >= 0 )
              v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, v6, v11);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( this == (BrowserToolWindow *)-176LL )
          {
            v16 = v19;
          }
          else
          {
            if ( v14 < 0 )
            {
              v15 = 0;
              v16 = v19;
            }
            else
            {
              v15 = v19;
              v16 = 0;
              v19 = 0;
            }
            *((_QWORD *)this + 22) = v15;
          }
          if ( v16 )
            (*((void (__fastcall **)(struct tagCREATESTRUCTW *))v16->lpCreateParams + 2))(v16);
          if ( !v14 && !(unsigned int)WPCHost::AdviseEvents(*((WPCHost **)this + 17)) )
          {
            v17 = *(_QWORD *)(*((_QWORD *)this + 17) + 104LL);
            if ( v17 )
            {
              if ( !(*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 144LL))(v17, (char *)this + 144) )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
                return 0;
              }
            }
          }
        }
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000ec34  mov     [rsp-28h+arg_0], rbx
0x18000ec39  mov     [rsp-28h+arg_8], rdx
0x18000ec3e  push    rbp
0x18000ec3f  push    rsi
0x18000ec40  push    rdi
0x18000ec41  push    r14
0x18000ec43  push    r15
0x18000ec45  mov     rbp, rsp
0x18000ec48  sub     rsp, 20h
0x18000ec4c  mov     rdi, rcx
0x18000ec4f  call    AtlAxWinInit
0x18000ec54  test    eax, eax
0x18000ec56  jz      loc_18000EE72
0x18000ec5c  xor     ecx, ecx; pvReserved
0x18000ec5e  call    cs:__imp_OleInitialize
0x18000ec64  mov     [rbp+arg_8], 0
0x18000ec6c  lea     rcx, [rbp+arg_8]
0x18000ec70  call    ?CreateInstance@?$CComObject@VWPCHost@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<WPCHost>::CreateInstance(ATL::CComObject<WPCHost> * *)
0x18000ec75  mov     esi, eax
0x18000ec77  mov     rbx, [rbp+arg_8]
0x18000ec7b  cmp     [rdi+88h], rbx
0x18000ec82  jz      short loc_18000ECB7
0x18000ec84  test    rbx, rbx
0x18000ec87  jz      short loc_18000EC98
0x18000ec89  mov     rcx, [rbx]
0x18000ec8c  mov     rax, [rcx+8]
0x18000ec90  mov     rcx, rbx
0x18000ec93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec98  mov     rcx, [rdi+88h]
0x18000ec9f  mov     [rdi+88h], rbx
0x18000eca6  test    rcx, rcx
0x18000eca9  jz      short loc_18000ECB7
0x18000ecab  mov     rax, [rcx]
0x18000ecae  mov     rax, [rax+10h]
0x18000ecb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecb7  test    esi, esi
0x18000ecb9  jnz     loc_18000EE72
0x18000ecbf  xor     ebx, ebx
0x18000ecc1  mov     [rbp+arg_18], rbx
0x18000ecc5  mov     r14, [rdi+88h]
0x18000eccc  mov     rax, rdi
0x18000eccf  lea     rcx, [rdi+48h]
0x18000ecd3  neg     rax
0x18000ecd6  sbb     rsi, rsi
0x18000ecd9  and     rsi, rcx
0x18000ecdc  cmp     [r14+60h], rsi
0x18000ece0  jz      short loc_18000ED0F
0x18000ece2  test    rsi, rsi
0x18000ece5  jz      short loc_18000ECF6
0x18000ece7  mov     rax, [rsi]
0x18000ecea  mov     rcx, rsi
0x18000eced  mov     rax, [rax+8]
0x18000ecf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecf6  mov     rcx, [r14+60h]
0x18000ecfa  test    rcx, rcx
0x18000ecfd  jz      short loc_18000ED0B
0x18000ecff  mov     rax, [rcx]
0x18000ed02  mov     rax, [rax+10h]
0x18000ed06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed0b  mov     [r14+60h], rsi
0x18000ed0f  lea     rdx, [rdi+0A8h]
0x18000ed16  mov     rcx, r14
0x18000ed19  call    ?CreateWebPlatformControl@WPCHost@@AEAAJAEAV?$CComPtr@UIDispatchEx@@@ATL@@@Z; WPCHost::CreateWebPlatformControl(ATL::CComPtr<IDispatchEx> &)
0x18000ed1e  test    eax, eax
0x18000ed20  jnz     loc_18000EE72
0x18000ed26  mov     rsi, [r14+68h]
0x18000ed2a  test    rsi, rsi
0x18000ed2d  jz      short loc_18000ED45
0x18000ed2f  mov     rax, [rsi]
0x18000ed32  mov     rcx, rsi
0x18000ed35  mov     rax, [rax+8]
0x18000ed39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed3e  mov     rbx, rsi
0x18000ed41  mov     [rbp+arg_18], rbx
0x18000ed45  mov     r15, [rdi+8]
0x18000ed49  call    AtlAxWinInit
0x18000ed4e  test    rbx, rbx
0x18000ed51  jz      loc_18000EE70
0x18000ed57  lea     r14, [rdi+0B0h]
0x18000ed5e  mov     [rbp+arg_8], 0
0x18000ed66  lea     r8, [rbp+arg_8]
0x18000ed6a  call    ?CreateInstance@?$CComCreator@V?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComPolyObject<ATL::CAxHostWindow>>::CreateInstance(void *,_GUID const &,void * *)
0x18000ed6f  mov     esi, eax
0x18000ed71  test    eax, eax
0x18000ed73  js      short loc_18000EDCB
0x18000ed75  mov     [rbp+arg_10], 0
0x18000ed7d  mov     rcx, [rbp+arg_8]
0x18000ed81  mov     rax, [rcx]
0x18000ed84  lea     r8, [rbp+arg_10]
0x18000ed88  lea     rdx, _GUID_b6ea2050_048a_11d1_82b9_00c04fb9942e
0x18000ed8f  mov     rax, [rax]
0x18000ed92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed97  mov     esi, eax
0x18000ed99  test    eax, eax
0x18000ed9b  js      short loc_18000EDB5
0x18000ed9d  mov     rcx, [rbp+arg_10]
0x18000eda1  mov     rax, [rcx]
0x18000eda4  mov     r8, r15
0x18000eda7  mov     rdx, rbx
0x18000edaa  mov     rax, [rax+28h]
0x18000edae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb3  mov     esi, eax
0x18000edb5  mov     rcx, [rbp+arg_10]
0x18000edb9  test    rcx, rcx
0x18000edbc  jz      short loc_18000EDCB
0x18000edbe  mov     rax, [rcx]
0x18000edc1  mov     rax, [rax+10h]
0x18000edc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edca  nop
0x18000edcb  test    r14, r14
0x18000edce  jz      short loc_18000EDEB
0x18000edd0  test    esi, esi
0x18000edd2  js      short loc_18000EDE0
0x18000edd4  mov     rax, [rbp+arg_8]
0x18000edd8  xor     ecx, ecx
0x18000edda  mov     [rbp+arg_8], rcx
0x18000edde  jmp     short loc_18000EDE6
0x18000ede0  xor     eax, eax
0x18000ede2  mov     rcx, [rbp+arg_8]
0x18000ede6  mov     [r14], rax
0x18000ede9  jmp     short loc_18000EDEF
0x18000edeb  mov     rcx, [rbp+arg_8]
0x18000edef  test    rcx, rcx
0x18000edf2  jz      short loc_18000EE01
0x18000edf4  mov     rax, [rcx]
0x18000edf7  mov     rax, [rax+10h]
0x18000edfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee00  nop
0x18000ee01  test    esi, esi
0x18000ee03  jnz     short loc_18000EE70
0x18000ee05  mov     rcx, [rdi+88h]; this
0x18000ee0c  call    ?AdviseEvents@WPCHost@@QEAAJXZ; WPCHost::AdviseEvents(void)
0x18000ee11  test    eax, eax
0x18000ee13  jz      short loc_18000EE2B
0x18000ee15  test    rbx, rbx
0x18000ee18  jz      short loc_18000EE72
0x18000ee1a  mov     rax, [rbx]
0x18000ee1d  mov     rcx, rbx
0x18000ee20  mov     rax, [rax+10h]
0x18000ee24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee29  jmp     short loc_18000EE72
0x18000ee2b  mov     rax, [rdi+88h]
0x18000ee32  mov     rcx, [rax+68h]
0x18000ee36  test    rcx, rcx
0x18000ee39  jz      short loc_18000EE6E
0x18000ee3b  mov     rax, [rcx]
0x18000ee3e  lea     rdx, [rdi+90h]
0x18000ee45  mov     rax, [rax+90h]
0x18000ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee51  test    eax, eax
0x18000ee53  jnz     short loc_18000EE6E
0x18000ee55  test    rbx, rbx
0x18000ee58  jz      short loc_18000EE6A
0x18000ee5a  mov     rax, [rbx]
0x18000ee5d  mov     rcx, rbx
0x18000ee60  mov     rax, [rax+10h]
0x18000ee64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee69  nop
0x18000ee6a  xor     eax, eax
0x18000ee6c  jmp     short loc_18000EE75
0x18000ee6e  jmp     short loc_18000EE15
0x18000ee70  jmp     short loc_18000EE15
0x18000ee72  or      eax, 0FFFFFFFFh
0x18000ee75  mov     rbx, [rsp+20h+arg_0]
0x18000ee7a  add     rsp, 20h
0x18000ee7e  pop     r15
0x18000ee80  pop     r14
0x18000ee82  pop     rdi
0x18000ee83  pop     rsi
0x18000ee84  pop     rbp
0x18000ee85  retn
```
