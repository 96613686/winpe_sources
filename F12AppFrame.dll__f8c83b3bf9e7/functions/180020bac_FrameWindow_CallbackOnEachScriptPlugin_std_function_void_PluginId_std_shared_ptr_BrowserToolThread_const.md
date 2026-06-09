# FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)

- ea: `0x180020bac`
- end: `0x180020dc6`
- name: `?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z`
- size: `538`
- prototype: `_BYTE *__fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800240e4`
- `0x180024d00`
- `0x180024fa8`
- `0x1800256c0`
- `0x1800257e0`
- `0x1800263e8`
- `0x18002874c`
- `0x180028978`
- `0x180028a60`
- `0x18002b910`

## callees

- `0x180001800`
- `0x180020bac`
- `0x180022f44`
- `0x180035010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180020d27`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180020d27`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BYTE *__fastcall FrameWindow::CallbackOnEachScriptPlugin(__int64 a1, __int64 a2)
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
    if ( (unsigned __int8)FrameWindow::IsPluginLoaded(v20, *((unsigned int *)v5 + 8)) && (_DWORD)a2 != 8 )
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
0x180020bac  push    rbp
0x180020bae  push    rbx
0x180020baf  push    rsi
0x180020bb0  push    rdi
0x180020bb1  lea     rbp, [rsp-3Fh]
0x180020bb6  sub     rsp, 0F8h
0x180020bbd  mov     rax, cs:__security_cookie
0x180020bc4  xor     rax, rsp
0x180020bc7  mov     [rbp+57h+var_30], rax
0x180020bcb  mov     rdi, rcx
0x180020bce  lea     rax, [rbp+57h+var_D0]
0x180020bd2  mov     [rsp+110h+var_F0], rax
0x180020bd7  mov     [rbp+57h+var_98], 0
0x180020bdf  mov     rcx, [rdx+38h]
0x180020be3  test    rcx, rcx
0x180020be6  jz      short loc_180020BFB
0x180020be8  mov     rax, [rcx]
0x180020beb  lea     rdx, [rbp+57h+var_D0]
0x180020bef  mov     rax, [rax]
0x180020bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf7  mov     [rbp+57h+var_98], rax
0x180020bfb  mov     [rbp+57h+var_90], rdi
0x180020bff  lea     rax, [rbp+57h+var_D0]
0x180020c03  mov     [rbp+57h+var_88], rax
0x180020c07  mov     rdi, [rdi+1C0h]
0x180020c0e  mov     rbx, [rdi]
0x180020c11  cmp     rbx, rdi
0x180020c14  jz      loc_180020D2E
0x180020c1a  mov     edx, [rbx+20h]
0x180020c1d  mov     rcx, [rbp+57h+var_90]
0x180020c21  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x180020c26  test    al, al
0x180020c28  jz      loc_180020CD8
0x180020c2e  cmp     edx, 8
0x180020c31  jz      loc_180020CD8
0x180020c37  mov     rcx, [rbx+28h]
0x180020c3b  xorps   xmm0, xmm0
0x180020c3e  movdqu  [rsp+110h+var_E8], xmm0
0x180020c44  mov     rax, [rcx+8]
0x180020c48  test    rax, rax
0x180020c4b  jz      short loc_180020C51
0x180020c4d  lock inc dword ptr [rax+8]
0x180020c51  mov     rax, [rcx]
0x180020c54  mov     qword ptr [rsp+110h+var_E8], rax
0x180020c59  mov     rax, [rcx+8]
0x180020c5d  mov     qword ptr [rsp+110h+var_E8+8], rax
0x180020c62  lea     rax, [rsp+110h+var_E8]
0x180020c67  mov     [rsp+110h+var_D8], rax
0x180020c6c  mov     eax, [rbx+20h]
0x180020c6f  mov     dword ptr [rsp+110h+var_F0], eax
0x180020c73  mov     rcx, [rbp+57h+var_98]
0x180020c77  test    rcx, rcx
0x180020c7a  jz      loc_180020D27
0x180020c80  mov     rax, [rcx]
0x180020c83  lea     r8, [rsp+110h+var_E8]
0x180020c88  lea     rdx, [rsp+110h+var_F0]
0x180020c8d  mov     rax, [rax+10h]
0x180020c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c96  nop
0x180020c97  mov     rsi, qword ptr [rsp+110h+var_E8+8]
0x180020c9c  test    rsi, rsi
0x180020c9f  jz      short loc_180020CD8
0x180020ca1  or      eax, 0FFFFFFFFh
0x180020ca4  lock xadd [rsi+8], eax
0x180020ca9  cmp     eax, 1
0x180020cac  jnz     short loc_180020CD8
0x180020cae  mov     rax, [rsi]
0x180020cb1  mov     rcx, rsi
0x180020cb4  mov     rax, [rax]
0x180020cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cbc  or      eax, 0FFFFFFFFh
0x180020cbf  lock xadd [rsi+0Ch], eax
0x180020cc4  cmp     eax, 1
0x180020cc7  jnz     short loc_180020CD8
0x180020cc9  mov     rax, [rsi]
0x180020ccc  mov     rcx, rsi
0x180020ccf  mov     rax, [rax+8]
0x180020cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cd8  mov     rcx, [rbx+10h]
0x180020cdc  cmp     byte ptr [rcx+19h], 0
0x180020ce0  jz      short loc_180020D03
0x180020ce2  mov     rax, [rbx+8]
0x180020ce6  jmp     short loc_180020CF5
0x180020ce8  cmp     rbx, [rax+10h]
0x180020cec  jnz     short loc_180020CFB
0x180020cee  mov     rbx, rax
0x180020cf1  mov     rax, [rax+8]
0x180020cf5  cmp     byte ptr [rax+19h], 0
0x180020cf9  jz      short loc_180020CE8
0x180020cfb  mov     rbx, rax
0x180020cfe  jmp     loc_180020C11
0x180020d03  mov     rbx, rcx
0x180020d06  mov     rcx, [rcx]
0x180020d09  cmp     byte ptr [rcx+19h], 0
0x180020d0d  jnz     loc_180020C11
0x180020d13  mov     rbx, rcx
0x180020d16  mov     rax, [rcx]
0x180020d19  mov     rcx, rax
0x180020d1c  cmp     byte ptr [rax+19h], 0
0x180020d20  jz      short loc_180020D13
0x180020d22  jmp     loc_180020C11
0x180020d27  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180020d2d  nop
0x180020d2e  lea     rax, [rbp+57h+var_80]
0x180020d32  mov     [rsp+110h+var_D8], rax
0x180020d37  xor     r8d, r8d
0x180020d3a  mov     [rbp+57h+var_48], r8
0x180020d3e  mov     rcx, [rbp+57h+var_98]
0x180020d42  test    rcx, rcx
0x180020d45  jz      short loc_180020D5D
0x180020d47  mov     rax, [rcx]
0x180020d4a  lea     rdx, [rbp+57h+var_80]
0x180020d4e  mov     rax, [rax]
0x180020d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d56  mov     r8, rax
0x180020d59  mov     [rbp+57h+var_48], rax
0x180020d5d  mov     rcx, [rbp+57h+var_90]
0x180020d61  mov     [rbp+57h+var_40], rcx
0x180020d65  mov     rcx, [rbp+57h+var_98]
0x180020d69  test    rcx, rcx
0x180020d6c  jz      short loc_180020D90
0x180020d6e  mov     rax, [rcx]
0x180020d71  lea     rdx, [rbp+57h+var_D0]
0x180020d75  cmp     rcx, rdx
0x180020d78  setnz   dl
0x180020d7b  mov     rax, [rax+20h]
0x180020d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d84  mov     [rbp+57h+var_98], 0
0x180020d8c  mov     r8, [rbp+57h+var_48]
0x180020d90  test    r8, r8
0x180020d93  jz      short loc_180020DAE
0x180020d95  mov     rax, [r8]
0x180020d98  lea     rcx, [rbp+57h+var_80]
0x180020d9c  cmp     r8, rcx
0x180020d9f  setnz   dl
0x180020da2  mov     rcx, r8
0x180020da5  mov     rax, [rax+20h]
0x180020da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dae  mov     rcx, [rbp+57h+var_30]
0x180020db2  xor     rcx, rsp; StackCookie
0x180020db5  call    __security_check_cookie
0x180020dba  add     rsp, 0F8h
0x180020dc1  pop     rdi
0x180020dc2  pop     rsi
0x180020dc3  pop     rbx
0x180020dc4  pop     rbp
0x180020dc5  retn
```
