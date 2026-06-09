# CDPComMessagingHost::Start(CDPComAppId *,ICDPComMessagingHostHandler *,char const *)

- ea: `0x180039940`
- end: `0x180039a6e`
- name: `?Start@CDPComMessagingHost@@UEAAJPEAUCDPComAppId@@PEAUICDPComMessagingHostHandler@@PEBD@Z`
- size: `302`
- prototype: `__int64 __fastcall(CDPComMessagingHost *this, struct CDPComAppId *, struct ICDPComMessagingHostHandler *, const char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003e60`
- `0x18000ad1c`
- `0x18000cb8c`
- `0x180017dcc`
- `0x1800225d0`
- `0x180039384`
- `0x180039424`
- `0x180039940`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180039a36`
- `msvcp_win!_Mtx_unlock` at `0x180039a36`
- `cdp!CDPCreateMessagingHostInternal` at `0x180039a21`
- `cdp!CDPCreateMessagingHostInternal` at `0x180039a21`
- `cdp!CDPCreateAppId` at `0x1800399b8`
- `cdp!CDPCreateAppId` at `0x1800399b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComMessagingHost::Start(
        CDPComMessagingHost *this,
        struct CDPComAppId *a2,
        struct ICDPComMessagingHostHandler *a3,
        const char *a4)
{
  __int64 v7; // rcx
  int v8; // edi
  CDPComMessagingHost::MessagingCallback *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base **v14; // [rsp+38h] [rbp-30h]
  std::_Ref_count_base *v15[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v17; // [rsp+58h] [rbp-10h]

  if ( !a3 || !a2 )
    return 2147942487LL;
  *(_OWORD *)v15 = 0;
  v14 = v15;
  v13 = 0;
  v7 = *(unsigned int *)a2;
  if ( (_DWORD)v7 || *((_QWORD *)a2 + 1) || *((_WORD *)a2 + 8) || *((_QWORD *)a2 + 3) )
    v8 = CDPCreateAppId(v7, *((_QWORD *)a2 + 1), *((unsigned __int16 *)a2 + 8), *((_QWORD *)a2 + 3), &v13);
  else
    v8 = -2147024809;
  cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(&v13);
  if ( v8 >= 0 )
  {
    v9 = (CDPComMessagingHost::MessagingCallback *)operator new(0x38u);
    v10 = CDPComMessagingHost::MessagingCallback::MessagingCallback(v9, a3);
    cdp::detail::wrap_unknown<CDPComMessagingHost::MessagingCallback>(&v16, v10);
    v11 = v16;
    if ( v16 )
    {
      std::_Mutex_base::lock((CDPComMessagingHost *)((char *)this + 40));
      v13 = 0;
      v14 = (std::_Ref_count_base **)((char *)this + 24);
      v8 = CDPCreateMessagingHostInternal(v15[0], v11, a4, &v13);
      cdp::detail::address_of<ICDPMessagingHost>::~address_of<ICDPMessagingHost>(&v13);
      _Mtx_unlock((CDPComMessagingHost *)((char *)this + 40));
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
  }
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039940  push    rbp
0x180039942  push    rbx
0x180039943  push    rsi
0x180039944  push    rdi
0x180039945  push    r14
0x180039947  push    r15
0x180039949  mov     rbp, rsp
0x18003994c  sub     rsp, 68h
0x180039950  mov     r14, r9
0x180039953  mov     rbx, r8
0x180039956  mov     rsi, rcx
0x180039959  xor     r15d, r15d
0x18003995c  test    r8, r8
0x18003995f  jz      loc_180039A5C
0x180039965  test    rdx, rdx
0x180039968  jz      loc_180039A5C
0x18003996e  xorps   xmm0, xmm0
0x180039971  movdqu  xmmword ptr [rbp+var_28], xmm0
0x180039976  lea     rax, [rbp+var_28]
0x18003997a  mov     [rbp+var_30], rax
0x18003997e  mov     [rbp+var_38], r15
0x180039982  mov     ecx, [rdx]
0x180039984  test    ecx, ecx
0x180039986  jnz     short loc_1800399A2
0x180039988  cmp     [rdx+8], r15
0x18003998c  jnz     short loc_1800399A2
0x18003998e  cmp     [rdx+10h], r15w
0x180039993  jnz     short loc_1800399A2
0x180039995  cmp     [rdx+18h], r15
0x180039999  jnz     short loc_1800399A2
0x18003999b  mov     edi, 80070057h
0x1800399a0  jmp     short loc_1800399C0
0x1800399a2  lea     rax, [rbp+var_38]
0x1800399a6  mov     [rsp+68h+var_48], rax
0x1800399ab  mov     r9, [rdx+18h]
0x1800399af  movzx   r8d, word ptr [rdx+10h]
0x1800399b4  mov     rdx, [rdx+8]
0x1800399b8  call    cs:__imp_CDPCreateAppId
0x1800399be  mov     edi, eax
0x1800399c0  lea     rcx, [rbp+var_38]
0x1800399c4  call    ??1?$address_of@VICDPAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(void)
0x1800399c9  test    edi, edi
0x1800399cb  js      short loc_180039A4A
0x1800399cd  mov     ecx, 38h ; '8'; Size
0x1800399d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800399d7  mov     rdx, rbx; struct ICDPComMessagingHostHandler *
0x1800399da  mov     rcx, rax; this
0x1800399dd  call    ??0MessagingCallback@CDPComMessagingHost@@QEAA@PEAUICDPComMessagingHostHandler@@@Z; CDPComMessagingHost::MessagingCallback::MessagingCallback(ICDPComMessagingHostHandler *)
0x1800399e2  mov     rdx, rax
0x1800399e5  lea     rcx, [rbp+var_18]
0x1800399e9  call    ??$wrap_unknown@VMessagingCallback@CDPComMessagingHost@@@detail@cdp@@YA?AV?$shared_ptr@VMessagingCallback@CDPComMessagingHost@@@std@@PEAVMessagingCallback@CDPComMessagingHost@@_N@Z; cdp::detail::wrap_unknown<CDPComMessagingHost::MessagingCallback>(CDPComMessagingHost::MessagingCallback *,bool)
0x1800399ee  mov     rdi, [rbp+var_18]
0x1800399f2  test    rdi, rdi
0x1800399f5  jnz     short loc_1800399FE
0x1800399f7  mov     edi, 8007000Eh
0x1800399fc  jmp     short loc_180039A3C
0x1800399fe  lea     rcx, [rsi+28h]; this
0x180039a02  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180039a07  mov     [rbp+var_38], r15
0x180039a0b  lea     rax, [rsi+18h]
0x180039a0f  mov     [rbp+var_30], rax
0x180039a13  lea     r9, [rbp+var_38]
0x180039a17  mov     r8, r14
0x180039a1a  mov     rdx, rdi
0x180039a1d  mov     rcx, [rbp+var_28]
0x180039a21  call    cs:__imp_CDPCreateMessagingHostInternal
0x180039a27  mov     edi, eax
0x180039a29  lea     rcx, [rbp+var_38]
0x180039a2d  call    ??1?$address_of@VICDPMessagingHost@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPMessagingHost>::~address_of<ICDPMessagingHost>(void)
0x180039a32  lea     rcx, [rsi+28h]; _Mtx_t
0x180039a36  call    cs:__imp__Mtx_unlock
0x180039a3c  mov     rcx, [rbp+var_10]; this
0x180039a40  test    rcx, rcx
0x180039a43  jz      short loc_180039A4A
0x180039a45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039a4a  mov     rcx, [rbp+var_28+8]; this
0x180039a4e  test    rcx, rcx
0x180039a51  jz      short loc_180039A58
0x180039a53  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180039a58  mov     eax, edi
0x180039a5a  jmp     short loc_180039A61
0x180039a5c  mov     eax, 80070057h
0x180039a61  add     rsp, 68h
0x180039a65  pop     r15
0x180039a67  pop     r14
0x180039a69  pop     rdi
0x180039a6a  pop     rsi
0x180039a6b  pop     rbx
0x180039a6c  pop     rbp
0x180039a6d  retn
```
