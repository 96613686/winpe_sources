# CMsMpComFactory::CreateAutoInstance(ushort *,IDispatch * *)

- ea: `0x180003380`
- end: `0x1800034f1`
- name: `?CreateAutoInstance@CMsMpComFactory@@UEAAJPEAGPEAPEAUIDispatch@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(CMsMpComFactory *this, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003380`
- `0x180004b7c`
- `0x180009440`
- `0x18000a010`

## import_xrefs

- `ole32!IIDFromString` at `0x1800033cd`
- `ole32!IIDFromString` at `0x1800033cd`

## pseudocode

```c
__int64 __fastcall CMsMpComFactory::CreateAutoInstance(
        CMsMpComFactory *this,
        unsigned __int16 *a2,
        struct IDispatch **a3)
{
  HRESULT v5; // ebx
  struct IDispatch *v7; // rax
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  struct IDispatch *v9; // [rsp+28h] [rbp-28h] BYREF
  IID iid; // [rsp+30h] [rbp-20h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  iid = 0;
  v5 = IIDFromString(a2, &iid);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids,
        (unsigned int)v5);
    return (unsigned int)v5;
  }
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(CMsMpComFactory *, IID *, __int64 *))(*(_QWORD *)this + 56LL))(this, &iid, &v8);
  if ( v5 < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return (unsigned int)v5;
  }
  v9 = 0;
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IDispatch **))v8)(
         v8,
         &GUID_00020400_0000_0000_c000_000000000046,
         &v9);
  if ( v5 < 0 )
  {
    if ( v9 )
      ((void (__fastcall *)(struct IDispatch *))v9->lpVtbl->Release)(v9);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    return (unsigned int)v5;
  }
  v7 = v9;
  v9 = 0;
  *a3 = v7;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x180003380  mov     [rsp-18h+arg_18], rbx
0x180003385  push    rbp
0x180003386  push    rsi
0x180003387  push    rdi
0x180003388  mov     rbp, rsp
0x18000338b  sub     rsp, 50h
0x18000338f  mov     rax, cs:__security_cookie
0x180003396  xor     rax, rsp
0x180003399  mov     [rbp+var_10], rax
0x18000339d  mov     rdi, r8
0x1800033a0  mov     rax, rdx
0x1800033a3  mov     rsi, rcx
0x1800033a6  test    rdx, rdx
0x1800033a9  jz      loc_1800034D0
0x1800033af  test    r8, r8
0x1800033b2  jz      loc_1800034D0
0x1800033b8  mov     qword ptr [r8], 0
0x1800033bf  xorps   xmm0, xmm0
0x1800033c2  movups  xmmword ptr [rbp+iid.Data1], xmm0
0x1800033c6  lea     rdx, [rbp+iid]; lpiid
0x1800033ca  mov     rcx, rax; lpsz
0x1800033cd  call    cs:__imp_IIDFromString
0x1800033d3  mov     ebx, eax
0x1800033d5  test    eax, eax
0x1800033d7  jns     short loc_180003411
0x1800033d9  lea     rax, WPP_GLOBAL_Control
0x1800033e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e7  cmp     rcx, rax
0x1800033ea  jz      short loc_18000340A
0x1800033ec  test    byte ptr [rcx+1Ch], 1
0x1800033f0  jz      short loc_18000340A
0x1800033f2  mov     edx, 0Bh
0x1800033f7  mov     r9d, ebx
0x1800033fa  lea     r8, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids
0x180003401  mov     rcx, [rcx+10h]
0x180003405  call    WPP_SF_d
0x18000340a  mov     eax, ebx
0x18000340c  jmp     loc_1800034D5
0x180003411  mov     [rbp+var_30], 0
0x180003419  mov     rax, [rsi]
0x18000341c  lea     r8, [rbp+var_30]
0x180003420  lea     rdx, [rbp+iid]
0x180003424  mov     rcx, rsi
0x180003427  mov     rax, [rax+38h]
0x18000342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003430  mov     ebx, eax
0x180003432  test    eax, eax
0x180003434  jns     short loc_18000344E
0x180003436  mov     rcx, [rbp+var_30]
0x18000343a  test    rcx, rcx
0x18000343d  jz      short loc_18000344C
0x18000343f  mov     rdx, [rcx]
0x180003442  mov     rax, [rdx+10h]
0x180003446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344b  nop
0x18000344c  jmp     short loc_18000340A
0x18000344e  mov     [rbp+var_28], 0
0x180003456  mov     rcx, [rbp+var_30]
0x18000345a  mov     rax, [rcx]
0x18000345d  lea     r8, [rbp+var_28]
0x180003461  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180003468  mov     rax, [rax]
0x18000346b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003470  mov     ebx, eax
0x180003472  test    eax, eax
0x180003474  jns     short loc_1800034A7
0x180003476  mov     rcx, [rbp+var_28]
0x18000347a  test    rcx, rcx
0x18000347d  jz      short loc_18000348C
0x18000347f  mov     rdx, [rcx]
0x180003482  mov     rax, [rdx+10h]
0x180003486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000348b  nop
0x18000348c  mov     rcx, [rbp+var_30]
0x180003490  test    rcx, rcx
0x180003493  jz      short loc_1800034A2
0x180003495  mov     rax, [rcx]
0x180003498  mov     rax, [rax+10h]
0x18000349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a1  nop
0x1800034a2  jmp     loc_18000340A
0x1800034a7  mov     rax, [rbp+var_28]
0x1800034ab  mov     [rbp+var_28], 0
0x1800034b3  mov     [rdi], rax
0x1800034b6  mov     rcx, [rbp+var_30]
0x1800034ba  test    rcx, rcx
0x1800034bd  jz      short loc_1800034CC
0x1800034bf  mov     rax, [rcx]
0x1800034c2  mov     rax, [rax+10h]
0x1800034c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034cb  nop
0x1800034cc  xor     eax, eax
0x1800034ce  jmp     short loc_1800034D5
0x1800034d0  mov     eax, 80004003h
0x1800034d5  mov     rcx, [rbp+var_10]
0x1800034d9  xor     rcx, rsp; StackCookie
0x1800034dc  call    __security_check_cookie
0x1800034e1  mov     rbx, [rsp+50h+arg_18]
0x1800034e9  add     rsp, 50h
0x1800034ed  pop     rdi
0x1800034ee  pop     rsi
0x1800034ef  pop     rbp
0x1800034f0  retn
```
