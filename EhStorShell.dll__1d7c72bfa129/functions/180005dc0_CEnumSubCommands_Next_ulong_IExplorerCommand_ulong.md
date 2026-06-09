# CEnumSubCommands::Next(ulong,IExplorerCommand * *,ulong *)

- ea: `0x180005dc0`
- end: `0x1800061e5`
- name: `?Next@CEnumSubCommands@@UEAAJKPEAPEAUIExplorerCommand@@PEAK@Z`
- size: `1061`
- prototype: `__int64 __fastcall(CEnumSubCommands *__hidden this, unsigned int, struct IExplorerCommand **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000453c`
- `0x180005b60`
- `0x180005dc0`
- `0x1800061ec`
- `0x1800064cc`
- `0x180006b8c`
- `0x18000a428`
- `0x18000a474`
- `0x18000b2e4`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Next(
        CEnumSubCommands *this,
        unsigned int a2,
        struct IExplorerCommand **a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  struct IUnknown **v8; // r12
  PVOID *v9; // rcx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int i; // edi
  struct IUnknown *v18; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdi
  _DWORD *v23; // rbx
  struct IExplorerCommand **v24; // r8
  unsigned int v26; // [rsp+30h] [rbp-30h] BYREF
  __int64 v27; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v31; // [rsp+A8h] [rbp+48h] BYREF
  struct IExplorerCommand **v32; // [rsp+B0h] [rbp+50h]
  int v33; // [rsp+B8h] [rbp+58h] BYREF

  v32 = a3;
  if ( a4 )
    *a4 = 0;
  v7 = 0;
  if ( a2 )
  {
    v8 = (struct IUnknown **)((char *)this + 32);
    while ( 1 )
    {
      v33 = 0;
      v31 = 0;
      (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &v33);
      if ( !*v8 )
        goto LABEL_9;
      ((void (__fastcall *)(struct IUnknown *, unsigned int *))(*v8)->lpVtbl[1].QueryInterface)(*v8, &v31);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        break;
LABEL_10:
      if ( *((_DWORD *)this + 10) == v31 )
      {
        if ( v9 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v9 + 28) & 0x20) != 0 )
          {
            WPP_SF_d(v9[2], 12, &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids, v31);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
          {
            WPP_SF_dd(v9[2], 13, &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids, *((unsigned int *)this + 6), v33);
            v9 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        if ( *((_DWORD *)this + 6) == v33 )
          goto LABEL_53;
        if ( *v8 )
          ATL::AtlComPtrAssign(v8, 0);
        *((_DWORD *)this + 10) = 0;
        v28 = 0;
        v10 = (__int64 *)*((_QWORD *)this + 2);
        v11 = *v10;
        v12 = *((unsigned int *)this + 6);
        *((_DWORD *)this + 6) = v12 + 1;
        v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 *))(v11 + 32))(
                v10,
                v12,
                &GUID_5aef78c6_2242_4703_bf49_44b29357a359,
                &v28);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)(*((_DWORD *)this + 6) - 1),
              (unsigned int)v13,
              *((_DWORD *)this + 6) - 1);
          goto LABEL_24;
        }
        v27 = 0;
        v26 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v28 + 32LL))(v28, &v27, &v26);
        if ( v14 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 15;
            goto LABEL_33;
          }
          goto LABEL_34;
        }
        v31 = v26;
        v14 = CObjectArray::Create<IEnhancedStorageSilo>(v27, v26, v8);
        if ( v14 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v16 = 16;
LABEL_33:
            WPP_SF_d(v15[2], v16, &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids, (unsigned int)v14);
          }
LABEL_34:
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v27);
LABEL_24:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
          goto LABEL_51;
        }
        for ( i = 0; i < v31; ++i )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v27 + 8LL * i) + 16LL))(*(_QWORD *)(v27 + 8LL * i));
          *(_QWORD *)(v27 + 8LL * i) = 0;
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v27);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
      }
      v29 = 0;
      v18 = *v8;
      lpVtbl = (*v8)->lpVtbl;
      v20 = *((unsigned int *)this + 10);
      *((_DWORD *)this + 10) = v20 + 1;
      v21 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, GUID *, __int64 *))lpVtbl[1].AddRef)(
              v18,
              v20,
              &GUID_b6f7f311_206f_4ff8_9c4b_27efee77a86f,
              &v29);
      if ( v21 >= 0 )
      {
        v30[0] = 0;
        v22 = v29;
        v23 = operator new(0x18u);
        v30[1] = v23;
        if ( v23 )
        {
          *(_QWORD *)v23 = &CSubCommand::`vftable';
          v23[2] = 1;
          *((_QWORD *)v23 + 2) = v22;
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
          v30[0] = v23;
          v24 = &v32[v7++];
          (**(void (__fastcall ***)(void *, GUID *, struct IExplorerCommand **))v23)(
            v23,
            &GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9,
            v24);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
          goto LABEL_51;
        }
        v30[0] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids,
            2147942414LL);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v30);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)(*((_DWORD *)this + 10) - 1),
          (unsigned int)v21,
          *((_DWORD *)this + 10) - 1);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
LABEL_51:
      if ( v7 >= a2 )
        goto LABEL_52;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids, v31);
LABEL_9:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
LABEL_52:
  v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_53:
  if ( a4 )
  {
    *a4 += v7;
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
    WPP_SF_d(v9[2], 19, &WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids, v7);
  return v7 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180005dc0  mov     [rsp-38h+arg_0], rbx
0x180005dc5  mov     [rsp-38h+arg_10], r8
0x180005dca  push    rbp
0x180005dcb  push    rsi
0x180005dcc  push    rdi
0x180005dcd  push    r12
0x180005dcf  push    r13
0x180005dd1  push    r14
0x180005dd3  push    r15
0x180005dd5  mov     rbp, rsp
0x180005dd8  sub     rsp, 60h
0x180005ddc  mov     r15, r9
0x180005ddf  mov     r13d, edx
0x180005de2  mov     r14, rcx
0x180005de5  xor     ebx, ebx
0x180005de7  test    r9, r9
0x180005dea  jz      short loc_180005DEF
0x180005dec  mov     [r9], ebx
0x180005def  mov     esi, ebx
0x180005df1  lea     rdi, WPP_GLOBAL_Control
0x180005df8  test    r13d, r13d
0x180005dfb  jz      loc_180006189
0x180005e01  lea     r12, [rcx+20h]
0x180005e05  mov     [rbp+arg_18], ebx
0x180005e08  mov     [rbp+arg_8], ebx
0x180005e0b  mov     rcx, [r14+10h]
0x180005e0f  mov     rax, [rcx]
0x180005e12  lea     rdx, [rbp+arg_18]
0x180005e16  mov     rax, [rax+18h]
0x180005e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1f  mov     rcx, [r12]
0x180005e23  test    rcx, rcx
0x180005e26  jz      short loc_180005E63
0x180005e28  mov     rax, [rcx]
0x180005e2b  lea     rdx, [rbp+arg_8]
0x180005e2f  mov     rax, [rax+18h]
0x180005e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e3f  cmp     rcx, rdi
0x180005e42  jz      short loc_180005E6A
0x180005e44  test    byte ptr [rcx+1Ch], 20h
0x180005e48  jz      short loc_180005E6A
0x180005e4a  mov     edx, 0Bh
0x180005e4f  mov     r9d, [rbp+arg_8]
0x180005e53  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x180005e5a  mov     rcx, [rcx+10h]
0x180005e5e  call    WPP_SF_d
0x180005e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e6a  mov     r9d, [rbp+arg_8]
0x180005e6e  cmp     [r14+28h], r9d
0x180005e72  jnz     loc_180006036
0x180005e78  cmp     rcx, rdi
0x180005e7b  jz      short loc_180005ED1
0x180005e7d  test    byte ptr [rcx+1Ch], 20h
0x180005e81  jz      short loc_180005E9F
0x180005e83  mov     edx, 0Ch
0x180005e88  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x180005e8f  mov     rcx, [rcx+10h]
0x180005e93  call    WPP_SF_d
0x180005e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e9f  cmp     rcx, rdi
0x180005ea2  jz      short loc_180005ED1
0x180005ea4  test    byte ptr [rcx+1Ch], 20h
0x180005ea8  jz      short loc_180005ED1
0x180005eaa  mov     edx, 0Dh
0x180005eaf  mov     eax, [rbp+arg_18]
0x180005eb2  mov     [rsp+60h+var_40], eax
0x180005eb6  mov     r9d, [r14+18h]
0x180005eba  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x180005ec1  mov     rcx, [rcx+10h]
0x180005ec5  call    WPP_SF_dd
0x180005eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ed1  mov     eax, [rbp+arg_18]
0x180005ed4  cmp     [r14+18h], eax
0x180005ed8  jz      loc_180006190
0x180005ede  cmp     [r12], rbx
0x180005ee2  jz      short loc_180005EEE
0x180005ee4  xor     edx, edx; struct IUnknown *
0x180005ee6  mov     rcx, r12; struct IUnknown **
0x180005ee9  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180005eee  mov     [r14+28h], ebx
0x180005ef2  mov     [rbp+var_20], rbx
0x180005ef6  mov     rcx, [r14+10h]
0x180005efa  mov     rax, [rcx]
0x180005efd  mov     edx, [r14+18h]
0x180005f01  lea     r8d, [rdx+1]
0x180005f05  mov     [r14+18h], r8d
0x180005f09  lea     r9, [rbp+var_20]
0x180005f0d  lea     r8, _GUID_5aef78c6_2242_4703_bf49_44b29357a359
0x180005f14  mov     rax, [rax+20h]
0x180005f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1d  test    eax, eax
0x180005f1f  jns     short loc_180005F5F
0x180005f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f28  cmp     rcx, rdi
0x180005f2b  jz      short loc_180005F51
0x180005f2d  test    byte ptr [rcx+1Ch], 2
0x180005f31  jz      short loc_180005F51
0x180005f33  mov     r8d, [r14+18h]
0x180005f37  dec     r8d
0x180005f3a  mov     edx, 0Eh
0x180005f3f  mov     [rsp+60h+var_40], r8d
0x180005f44  mov     r9d, eax
0x180005f47  mov     rcx, [rcx+10h]
0x180005f4b  call    WPP_SF_Dd
0x180005f50  nop
0x180005f51  lea     rcx, [rbp+var_20]
0x180005f55  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005f5a  jmp     loc_180006180
0x180005f5f  mov     [rbp+var_28], rbx
0x180005f63  mov     [rbp+var_30], ebx
0x180005f66  mov     rcx, [rbp+var_20]
0x180005f6a  mov     rax, [rcx]
0x180005f6d  lea     r8, [rbp+var_30]
0x180005f71  lea     rdx, [rbp+var_28]
0x180005f75  mov     rax, [rax+20h]
0x180005f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7e  test    eax, eax
0x180005f80  jns     short loc_180005F9B
0x180005f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f89  cmp     rcx, rdi
0x180005f8c  jz      short loc_180005FDC
0x180005f8e  test    byte ptr [rcx+1Ch], 2
0x180005f92  jz      short loc_180005FDC
0x180005f94  mov     edx, 0Fh
0x180005f99  jmp     short loc_180005FC8
0x180005f9b  mov     edx, [rbp+var_30]
0x180005f9e  mov     [rbp+arg_8], edx
0x180005fa1  mov     r8, r12
0x180005fa4  mov     rcx, [rbp+var_28]
0x180005fa8  call    ??$Create@UIEnhancedStorageSilo@@@CObjectArray@@SAJPEAPEAUIEnhancedStorageSilo@@KPEAPEAUIObjectArray@@@Z; CObjectArray::Create<IEnhancedStorageSilo>(IEnhancedStorageSilo * *,ulong,IObjectArray * *)
0x180005fad  test    eax, eax
0x180005faf  jns     short loc_180005FEA
0x180005fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fb8  cmp     rcx, rdi
0x180005fbb  jz      short loc_180005FDC
0x180005fbd  test    byte ptr [rcx+1Ch], 2
0x180005fc1  jz      short loc_180005FDC
0x180005fc3  mov     edx, 10h
0x180005fc8  mov     r9d, eax
0x180005fcb  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x180005fd2  mov     rcx, [rcx+10h]
0x180005fd6  call    WPP_SF_d
0x180005fdb  nop
0x180005fdc  lea     rcx, [rbp+var_28]
0x180005fe0  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180005fe5  jmp     loc_180005F51
0x180005fea  mov     edi, ebx
0x180005fec  cmp     [rbp+arg_8], ebx
0x180005fef  jbe     short loc_18000601C
0x180005ff1  mov     ebx, edi
0x180005ff3  mov     rax, [rbp+var_28]
0x180005ff7  mov     rcx, [rax+rbx*8]
0x180005ffb  mov     rax, [rcx]
0x180005ffe  mov     rax, [rax+10h]
0x180006002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006007  mov     rax, [rbp+var_28]
0x18000600b  mov     qword ptr [rax+rbx*8], 0
0x180006013  inc     edi
0x180006015  cmp     edi, [rbp+arg_8]
0x180006018  jb      short loc_180005FF1
0x18000601a  xor     ebx, ebx
0x18000601c  lea     rcx, [rbp+var_28]
0x180006020  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180006025  nop
0x180006026  lea     rcx, [rbp+var_20]
0x18000602a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000602f  lea     rdi, WPP_GLOBAL_Control
0x180006036  mov     [rbp+var_18], rbx
0x18000603a  mov     rcx, [r12]
0x18000603e  mov     rax, [rcx]
0x180006041  mov     edx, [r14+28h]
0x180006045  lea     r8d, [rdx+1]
0x180006049  mov     [r14+28h], r8d
0x18000604d  lea     r9, [rbp+var_18]
0x180006051  lea     r8, _GUID_b6f7f311_206f_4ff8_9c4b_27efee77a86f
0x180006058  mov     rax, [rax+20h]
0x18000605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006061  test    eax, eax
0x180006063  jns     short loc_1800060A1
0x180006065  mov     rcx, cs:WPP_GLOBAL_Control
0x18000606c  cmp     rcx, rdi
0x18000606f  jz      loc_180006177
0x180006075  test    byte ptr [rcx+1Ch], 2
0x180006079  jz      loc_180006177
0x18000607f  mov     r8d, [r14+28h]
0x180006083  dec     r8d
0x180006086  mov     edx, 11h
0x18000608b  mov     [rsp+60h+var_40], r8d
0x180006090  mov     r9d, eax
0x180006093  mov     rcx, [rcx+10h]
0x180006097  call    WPP_SF_Dd
0x18000609c  jmp     loc_180006177
0x1800060a1  mov     [rbp+var_10], rbx
0x1800060a5  mov     rdi, [rbp+var_18]
0x1800060a9  mov     ecx, 18h; Size
0x1800060ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800060b3  mov     rbx, rax
0x1800060b6  mov     [rbp+var_8], rax
0x1800060ba  test    rax, rax
0x1800060bd  jz      short loc_180006132
0x1800060bf  lea     rax, ??_7CSubCommand@@6B@; const CSubCommand::`vftable'
0x1800060c6  mov     [rbx], rax
0x1800060c9  mov     dword ptr [rbx+8], 1
0x1800060d0  mov     [rbx+10h], rdi
0x1800060d4  test    rdi, rdi
0x1800060d7  jz      short loc_1800060E9
0x1800060d9  mov     rax, [rdi]
0x1800060dc  mov     rcx, rdi
0x1800060df  mov     rax, [rax+8]
0x1800060e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e8  nop
0x1800060e9  mov     [rbp+var_10], rbx
0x1800060ed  test    rbx, rbx
0x1800060f0  jz      short loc_180006138
0x1800060f2  mov     eax, esi
0x1800060f4  mov     rcx, [rbp+arg_10]
0x1800060f8  lea     r8, [rcx+rax*8]
0x1800060fc  inc     esi
0x1800060fe  mov     rax, [rbx]
0x180006101  lea     rdx, _GUID_a08ce4d0_fa25_44ab_b57c_c7b1c323e0b9
0x180006108  mov     rcx, rbx
0x18000610b  mov     rax, [rax]
0x18000610e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006113  nop
0x180006114  lea     rcx, [rbp+var_10]
0x180006118  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000611d  nop
0x18000611e  lea     rcx, [rbp+var_18]
0x180006122  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006127  xor     ebx, ebx
0x180006129  lea     rdi, WPP_GLOBAL_Control
0x180006130  jmp     short loc_180006180
0x180006132  xor     ebx, ebx
0x180006134  mov     [rbp+var_10], rbx
0x180006138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000613f  lea     rdi, WPP_GLOBAL_Control
0x180006146  cmp     rcx, rdi
0x180006149  jz      short loc_18000616D
0x18000614b  test    byte ptr [rcx+1Ch], 2
0x18000614f  jz      short loc_18000616D
0x180006151  mov     edx, 12h
0x180006156  mov     r9d, 8007000Eh
0x18000615c  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x180006163  mov     rcx, [rcx+10h]
0x180006167  call    WPP_SF_d
0x18000616c  nop
0x18000616d  lea     rcx, [rbp+var_10]
0x180006171  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006176  nop
0x180006177  lea     rcx, [rbp+var_18]
0x18000617b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006180  cmp     esi, r13d
0x180006183  jb      loc_180005E05
0x180006189  mov     rcx, cs:WPP_GLOBAL_Control
0x180006190  test    r15, r15
0x180006193  jz      short loc_18000619F
0x180006195  add     [r15], esi
0x180006198  mov     rcx, cs:WPP_GLOBAL_Control
0x18000619f  cmp     rcx, rdi
0x1800061a2  jz      short loc_1800061C2
0x1800061a4  test    byte ptr [rcx+1Ch], 2
0x1800061a8  jz      short loc_1800061C2
0x1800061aa  mov     edx, 13h
0x1800061af  mov     r9d, esi
0x1800061b2  lea     r8, WPP_3ed221a93b0b342b65b04ee5c2f92369_Traceguids
0x1800061b9  mov     rcx, [rcx+10h]
0x1800061bd  call    WPP_SF_d
0x1800061c2  neg     esi
0x1800061c4  sbb     eax, eax
0x1800061c6  not     eax
0x1800061c8  and     eax, 80004005h
0x1800061cd  mov     rbx, [rsp+60h+arg_0]
0x1800061d5  add     rsp, 60h
0x1800061d9  pop     r15
0x1800061db  pop     r14
0x1800061dd  pop     r13
0x1800061df  pop     r12
0x1800061e1  pop     rdi
0x1800061e2  pop     rsi
0x1800061e3  pop     rbp
0x1800061e4  retn
```
