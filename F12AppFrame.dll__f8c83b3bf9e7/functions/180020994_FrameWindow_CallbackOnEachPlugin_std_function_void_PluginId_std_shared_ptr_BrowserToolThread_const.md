# FrameWindow::CallbackOnEachPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)

- ea: `0x180020994`
- end: `0x180020ba5`
- name: `?CallbackOnEachPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z`
- size: `529`
- prototype: `_BYTE *__fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022a0c`
- `0x1800234d8`
- `0x180024ac4`
- `0x180028d38`

## callees

- `0x180001800`
- `0x180020994`
- `0x180022f44`
- `0x180035010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180020b06`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180020b06`

## pseudocode

```c
_BYTE *__fastcall FrameWindow::CallbackOnEachPlugin(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, _BYTE *); // rcx
  __int64 *v4; // rdi
  __int64 *v5; // rbx
  __int128 *v6; // rcx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rsi
  __int64 **v9; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _BYTE *result; // rax
  _BYTE *v13; // r8
  _BYTE *v14; // rdx
  _BYTE *v15; // [rsp+20h] [rbp-99h] BYREF
  __int128 v16; // [rsp+28h] [rbp-91h] BYREF
  __int128 *v17; // [rsp+38h] [rbp-81h]
  _BYTE v18[56]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE *v19; // [rsp+78h] [rbp-41h]
  __int64 v20; // [rsp+80h] [rbp-39h]
  _BYTE *v21; // [rsp+88h] [rbp-31h]
  _BYTE v22[56]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE *v23; // [rsp+C8h] [rbp+Fh]
  __int64 v24; // [rsp+D0h] [rbp+17h]

  v15 = v18;
  v19 = 0;
  v3 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
  if ( v3 )
    v19 = (_BYTE *)(**v3)(v3, v18);
  v20 = a1;
  v21 = v18;
  v4 = *(__int64 **)(a1 + 448);
  v5 = (__int64 *)*v4;
  while ( v5 != v4 )
  {
    if ( (unsigned __int8)FrameWindow::IsPluginLoaded(v20, *((unsigned int *)v5 + 8)) )
    {
      v6 = (__int128 *)v5[5];
      v16 = 0;
      v7 = *((_QWORD *)v6 + 1);
      if ( v7 )
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
      v16 = *v6;
      v17 = &v16;
      LODWORD(v15) = *((_DWORD *)v5 + 8);
      if ( !v19 )
      {
        std::_Xbad_function_call();
        break;
      }
      (*(void (__fastcall **)(_BYTE *, _BYTE **, __int128 *))(*(_QWORD *)v19 + 16LL))(v19, &v15, &v16);
      v8 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
      if ( *((_QWORD *)&v16 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
    }
    v9 = (__int64 **)v5[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v5 = i;
      v5 = i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  result = v22;
  v17 = (__int128 *)v22;
  v13 = 0;
  v23 = 0;
  if ( v19 )
  {
    result = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v19)(v19, v22);
    v13 = result;
    v23 = result;
  }
  v24 = v20;
  if ( v19 )
  {
    v14 = v18;
    LOBYTE(v14) = v19 != v18;
    result = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v14);
    v19 = 0;
    v13 = v23;
  }
  if ( v13 )
  {
    LOBYTE(a2) = v13 != v22;
    return (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v13 + 32LL))(v13, a2);
  }
  return result;
}

```

## disassembly

```asm
0x180020994  push    rbp
0x180020996  push    rbx
0x180020997  push    rsi
0x180020998  push    rdi
0x180020999  lea     rbp, [rsp-3Fh]
0x18002099e  sub     rsp, 0F8h
0x1800209a5  mov     rax, cs:__security_cookie
0x1800209ac  xor     rax, rsp
0x1800209af  mov     [rbp+57h+var_30], rax
0x1800209b3  mov     rdi, rcx
0x1800209b6  lea     rax, [rbp+57h+var_D0]
0x1800209ba  mov     [rsp+110h+var_F0], rax
0x1800209bf  mov     [rbp+57h+var_98], 0
0x1800209c7  mov     rcx, [rdx+38h]
0x1800209cb  test    rcx, rcx
0x1800209ce  jz      short loc_1800209E3
0x1800209d0  mov     rax, [rcx]
0x1800209d3  lea     rdx, [rbp+57h+var_D0]
0x1800209d7  mov     rax, [rax]
0x1800209da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209df  mov     [rbp+57h+var_98], rax
0x1800209e3  mov     [rbp+57h+var_90], rdi
0x1800209e7  lea     rax, [rbp+57h+var_D0]
0x1800209eb  mov     [rbp+57h+var_88], rax
0x1800209ef  mov     rdi, [rdi+1C0h]
0x1800209f6  mov     rbx, [rdi]
0x1800209f9  cmp     rbx, rdi
0x1800209fc  jz      loc_180020B0D
0x180020a02  mov     edx, [rbx+20h]
0x180020a05  mov     rcx, [rbp+57h+var_90]
0x180020a09  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x180020a0e  test    al, al
0x180020a10  jz      loc_180020AB7
0x180020a16  mov     rcx, [rbx+28h]
0x180020a1a  xorps   xmm0, xmm0
0x180020a1d  movdqu  [rsp+110h+var_E8], xmm0
0x180020a23  mov     rax, [rcx+8]
0x180020a27  test    rax, rax
0x180020a2a  jz      short loc_180020A30
0x180020a2c  lock inc dword ptr [rax+8]
0x180020a30  mov     rax, [rcx]
0x180020a33  mov     qword ptr [rsp+110h+var_E8], rax
0x180020a38  mov     rax, [rcx+8]
0x180020a3c  mov     qword ptr [rsp+110h+var_E8+8], rax
0x180020a41  lea     rax, [rsp+110h+var_E8]
0x180020a46  mov     [rsp+110h+var_D8], rax
0x180020a4b  mov     eax, [rbx+20h]
0x180020a4e  mov     dword ptr [rsp+110h+var_F0], eax
0x180020a52  mov     rcx, [rbp+57h+var_98]
0x180020a56  test    rcx, rcx
0x180020a59  jz      loc_180020B06
0x180020a5f  mov     rax, [rcx]
0x180020a62  lea     r8, [rsp+110h+var_E8]
0x180020a67  lea     rdx, [rsp+110h+var_F0]
0x180020a6c  mov     rax, [rax+10h]
0x180020a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a75  nop
0x180020a76  mov     rsi, qword ptr [rsp+110h+var_E8+8]
0x180020a7b  test    rsi, rsi
0x180020a7e  jz      short loc_180020AB7
0x180020a80  or      eax, 0FFFFFFFFh
0x180020a83  lock xadd [rsi+8], eax
0x180020a88  cmp     eax, 1
0x180020a8b  jnz     short loc_180020AB7
0x180020a8d  mov     rax, [rsi]
0x180020a90  mov     rcx, rsi
0x180020a93  mov     rax, [rax]
0x180020a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a9b  or      eax, 0FFFFFFFFh
0x180020a9e  lock xadd [rsi+0Ch], eax
0x180020aa3  cmp     eax, 1
0x180020aa6  jnz     short loc_180020AB7
0x180020aa8  mov     rax, [rsi]
0x180020aab  mov     rcx, rsi
0x180020aae  mov     rax, [rax+8]
0x180020ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ab7  mov     rcx, [rbx+10h]
0x180020abb  cmp     byte ptr [rcx+19h], 0
0x180020abf  jz      short loc_180020AE2
0x180020ac1  mov     rax, [rbx+8]
0x180020ac5  jmp     short loc_180020AD4
0x180020ac7  cmp     rbx, [rax+10h]
0x180020acb  jnz     short loc_180020ADA
0x180020acd  mov     rbx, rax
0x180020ad0  mov     rax, [rax+8]
0x180020ad4  cmp     byte ptr [rax+19h], 0
0x180020ad8  jz      short loc_180020AC7
0x180020ada  mov     rbx, rax
0x180020add  jmp     loc_1800209F9
0x180020ae2  mov     rbx, rcx
0x180020ae5  mov     rcx, [rcx]
0x180020ae8  cmp     byte ptr [rcx+19h], 0
0x180020aec  jnz     loc_1800209F9
0x180020af2  mov     rbx, rcx
0x180020af5  mov     rax, [rcx]
0x180020af8  mov     rcx, rax
0x180020afb  cmp     byte ptr [rax+19h], 0
0x180020aff  jz      short loc_180020AF2
0x180020b01  jmp     loc_1800209F9
0x180020b06  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180020b0c  nop
0x180020b0d  lea     rax, [rbp+57h+var_80]
0x180020b11  mov     [rsp+110h+var_D8], rax
0x180020b16  xor     r8d, r8d
0x180020b19  mov     [rbp+57h+var_48], r8
0x180020b1d  mov     rcx, [rbp+57h+var_98]
0x180020b21  test    rcx, rcx
0x180020b24  jz      short loc_180020B3C
0x180020b26  mov     rax, [rcx]
0x180020b29  lea     rdx, [rbp+57h+var_80]
0x180020b2d  mov     rax, [rax]
0x180020b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b35  mov     r8, rax
0x180020b38  mov     [rbp+57h+var_48], rax
0x180020b3c  mov     rcx, [rbp+57h+var_90]
0x180020b40  mov     [rbp+57h+var_40], rcx
0x180020b44  mov     rcx, [rbp+57h+var_98]
0x180020b48  test    rcx, rcx
0x180020b4b  jz      short loc_180020B6F
0x180020b4d  mov     rax, [rcx]
0x180020b50  lea     rdx, [rbp+57h+var_D0]
0x180020b54  cmp     rcx, rdx
0x180020b57  setnz   dl
0x180020b5a  mov     rax, [rax+20h]
0x180020b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b63  mov     [rbp+57h+var_98], 0
0x180020b6b  mov     r8, [rbp+57h+var_48]
0x180020b6f  test    r8, r8
0x180020b72  jz      short loc_180020B8D
0x180020b74  mov     rax, [r8]
0x180020b77  lea     rcx, [rbp+57h+var_80]
0x180020b7b  cmp     r8, rcx
0x180020b7e  setnz   dl
0x180020b81  mov     rcx, r8
0x180020b84  mov     rax, [rax+20h]
0x180020b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b8d  mov     rcx, [rbp+57h+var_30]
0x180020b91  xor     rcx, rsp; StackCookie
0x180020b94  call    __security_check_cookie
0x180020b99  add     rsp, 0F8h
0x180020ba0  pop     rdi
0x180020ba1  pop     rsi
0x180020ba2  pop     rbx
0x180020ba3  pop     rbp
0x180020ba4  retn
```
