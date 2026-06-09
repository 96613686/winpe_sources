# AVIStreamGetFrameOpen

- ea: `0x180014350`
- end: `0x180014462`
- name: `AVIStreamGetFrameOpen`
- size: `274`
- prototype: `PGETFRAME __stdcall(PAVISTREAM pavi, LPBITMAPINFOHEADER lpbiWanted)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049d0`
- `0x18000e664`
- `0x180011300`

## callees

- `0x180001008`
- `0x180001460`
- `0x180014350`
- `0x180018010`

## pseudocode

```c
PGETFRAME __stdcall AVIStreamGetFrameOpen(PAVISTREAM pavi, LPBITMAPINFOHEADER lpbiWanted)
{
  struct IAVIStreamVtbl *lpVtbl; // rax
  IGetFrame *v5; // rbx
  IGetFrame *v6; // rax
  IGetFrame *v8; // [rsp+40h] [rbp-28h] BYREF

  lpVtbl = pavi->lpVtbl;
  v8 = 0;
  ((void (__fastcall *)(PAVISTREAM, GUID *, IGetFrame **))lpVtbl->QueryInterface)(pavi, &IID_IGetFrame, &v8);
  v5 = v8;
  if ( !v8 )
  {
    v6 = (IGetFrame *)operator new(0x80u);
    v5 = v6;
    if ( !v6 )
      return 0;
    v6[3].lpVtbl = (struct IGetFrameVtbl *)pavi;
    v6->lpVtbl = (struct IGetFrameVtbl *)&GetFrameDef::`vftable';
    v6[1].lpVtbl = (struct IGetFrameVtbl *)1;
    LODWORD(v6[2].lpVtbl) = 0;
    LODWORD(v6[12].lpVtbl) = 0;
    LODWORD(v6[4].lpVtbl) = -4242;
    v6[5].lpVtbl = 0;
    v6[7].lpVtbl = 0;
    LODWORD(v6[6].lpVtbl) = 0;
    LODWORD(v6[8].lpVtbl) = 0;
    v6[9].lpVtbl = 0;
    v6[10].lpVtbl = 0;
    v6[11].lpVtbl = 0;
    ((void (__fastcall *)(PAVISTREAM))pavi->lpVtbl->AddRef)(pavi);
    v8 = v5;
  }
  if ( ((int (__fastcall *)(IGetFrame *, LPBITMAPINFOHEADER, _QWORD, _QWORD, _DWORD, int, int))v5->lpVtbl->SetFormat)(
         v5,
         lpbiWanted,
         0,
         0,
         0,
         -1,
         -1) < 0 )
  {
    ((void (__fastcall *)(IGetFrame *))v8->lpVtbl->Release)(v8);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180014350  mov     [rsp+arg_10], rbx
0x180014355  push    rbp
0x180014356  push    rsi
0x180014357  push    rdi
0x180014358  sub     rsp, 50h
0x18001435c  mov     rax, cs:__security_cookie
0x180014363  xor     rax, rsp
0x180014366  mov     [rsp+68h+var_20], rax
0x18001436b  mov     rax, [rcx]
0x18001436e  lea     r8, [rsp+68h+var_28]
0x180014373  mov     rsi, rdx
0x180014376  xor     ebp, ebp
0x180014378  lea     rdx, IID_IGetFrame
0x18001437f  mov     [rsp+68h+var_28], rbp
0x180014384  mov     rdi, rcx
0x180014387  mov     rax, [rax]
0x18001438a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001438f  mov     rbx, [rsp+68h+var_28]
0x180014394  test    rbx, rbx
0x180014397  jnz     short loc_180014400
0x180014399  mov     ecx, 80h; Size
0x18001439e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800143a3  mov     rbx, rax
0x1800143a6  test    rax, rax
0x1800143a9  jz      loc_18001443C
0x1800143af  lea     rax, ??_7GetFrameDef@@6B@; const GetFrameDef::`vftable'
0x1800143b6  mov     [rbx+18h], rdi
0x1800143ba  mov     [rbx], rax
0x1800143bd  mov     rcx, rdi
0x1800143c0  mov     qword ptr [rbx+8], 1
0x1800143c8  mov     [rbx+10h], ebp
0x1800143cb  mov     [rbx+60h], ebp
0x1800143ce  mov     dword ptr [rbx+20h], 0FFFFEF6Eh
0x1800143d5  mov     [rbx+28h], rbp
0x1800143d9  mov     [rbx+38h], rbp
0x1800143dd  mov     [rbx+30h], ebp
0x1800143e0  mov     [rbx+40h], ebp
0x1800143e3  mov     [rbx+48h], rbp
0x1800143e7  mov     [rbx+50h], rbp
0x1800143eb  mov     [rbx+58h], rbp
0x1800143ef  mov     rax, [rdi]
0x1800143f2  mov     rax, [rax+8]
0x1800143f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143fb  mov     [rsp+68h+var_28], rbx
0x180014400  mov     rax, [rbx]
0x180014403  or      ecx, 0FFFFFFFFh
0x180014406  mov     [rsp+68h+var_38], ecx
0x18001440a  xor     r9d, r9d
0x18001440d  mov     [rsp+68h+var_40], ecx
0x180014411  xor     r8d, r8d
0x180014414  mov     rdx, rsi
0x180014417  mov     [rsp+68h+var_48], ebp
0x18001441b  mov     rax, [rax+30h]
0x18001441f  mov     rcx, rbx
0x180014422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014427  test    eax, eax
0x180014429  jns     short loc_180014440
0x18001442b  mov     rcx, [rsp+68h+var_28]
0x180014430  mov     rax, [rcx]
0x180014433  mov     rax, [rax+10h]
0x180014437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001443c  xor     eax, eax
0x18001443e  jmp     short loc_180014445
0x180014440  mov     rax, [rsp+68h+var_28]
0x180014445  mov     rcx, [rsp+68h+var_20]
0x18001444a  xor     rcx, rsp; StackCookie
0x18001444d  call    __security_check_cookie
0x180014452  mov     rbx, [rsp+68h+arg_10]
0x18001445a  add     rsp, 50h
0x18001445e  pop     rdi
0x18001445f  pop     rsi
0x180014460  pop     rbp
0x180014461  retn
```
