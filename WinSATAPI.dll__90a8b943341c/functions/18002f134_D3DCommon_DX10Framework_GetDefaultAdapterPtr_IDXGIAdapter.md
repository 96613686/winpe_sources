# D3DCommon::DX10Framework::GetDefaultAdapterPtr(IDXGIAdapter * *)

- ea: `0x18002f134`
- end: `0x18002f2df`
- name: `?GetDefaultAdapterPtr@DX10Framework@D3DCommon@@SAJPEAPEAUIDXGIAdapter@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(struct IDXGIAdapter **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f0bc`

## callees

- `0x180013e69`
- `0x18002f134`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `dxgi!CreateDXGIFactory` at `0x18002f1a5`
- `dxgi!CreateDXGIFactory` at `0x18002f1a5`

## pseudocode

```c
HRESULT __fastcall D3DCommon::DX10Framework::GetDefaultAdapterPtr(struct IDXGIAdapter **a1)
{
  unsigned int v2; // r14d
  char v3; // si
  HRESULT result; // eax
  int v5; // ebx
  struct IDXGIAdapter *v6; // rcx
  struct IDXGIAdapter *v7; // [rsp+28h] [rbp-49h] BYREF
  __int64 v8; // [rsp+30h] [rbp-41h] BYREF
  void *ppFactory[2]; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v10[64]; // [rsp+48h] [rbp-29h] BYREF
  int v11; // [rsp+88h] [rbp+17h]
  int v12; // [rsp+8Ch] [rbp+1Bh]
  int v13; // [rsp+98h] [rbp+27h]

  ppFactory[1] = (void *)-2LL;
  v7 = 0;
  ppFactory[0] = 0;
  v8 = 0;
  memset_0(v10, 0, 0x60u);
  v2 = 0;
  v3 = 0;
  if ( !a1 )
    return -2147467261;
  result = CreateDXGIFactory(&GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369, ppFactory);
  if ( result >= 0 )
  {
    while ( 1 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, _QWORD, struct IDXGIAdapter **))(*(_QWORD *)ppFactory[0] + 56LL))(
             ppFactory[0],
             v2,
             &v7);
      if ( v5 < 0 )
        break;
      v5 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, _QWORD, __int64 *))v7->lpVtbl->EnumOutputs)(v7, 0, &v8);
      if ( v5 < 0 )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 56LL))(v8, v10);
      if ( v5 < 0 )
        break;
      if ( v13 && !v12 && !v11 )
      {
        *a1 = v7;
        v6 = 0;
        v7 = 0;
        v3 = 1;
        goto LABEL_13;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
      ((void (__fastcall *)(struct IDXGIAdapter *))v7->lpVtbl->Release)(v7);
      v7 = 0;
      ++v2;
    }
    v6 = v7;
LABEL_13:
    if ( v6 )
    {
      ((void (__fastcall *)(struct IDXGIAdapter *))v6->lpVtbl->Release)(v6);
      v7 = 0;
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
    }
    if ( ppFactory[0] )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory[0] + 16LL))(ppFactory[0]);
    if ( !v3 )
      *a1 = 0;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002f134  mov     rax, rsp
0x18002f137  push    rbp
0x18002f138  push    rdi
0x18002f139  push    r14
0x18002f13b  lea     rbp, [rax-5Fh]
0x18002f13f  sub     rsp, 0B0h
0x18002f146  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x18002f14e  mov     [rax+10h], rbx
0x18002f152  mov     [rax+18h], rsi
0x18002f156  mov     rax, cs:__security_cookie
0x18002f15d  xor     rax, rsp
0x18002f160  mov     [rbp+57h+var_20], rax
0x18002f164  mov     rdi, rcx
0x18002f167  and     [rbp+57h+var_A0], 0
0x18002f16c  and     [rbp+57h+ppFactory], 0
0x18002f171  and     [rbp+57h+var_98], 0
0x18002f176  xor     edx, edx; Val
0x18002f178  lea     r8d, [rdx+60h]; Size
0x18002f17c  lea     rcx, [rbp+57h+var_80]; void *
0x18002f180  call    memset_0
0x18002f185  xor     r14d, r14d
0x18002f188  xor     sil, sil
0x18002f18b  test    rdi, rdi
0x18002f18e  jnz     short loc_18002F19A
0x18002f190  mov     eax, 80004003h
0x18002f195  jmp     loc_18002F2BA
0x18002f19a  lea     rdx, [rbp+57h+ppFactory]; ppFactory
0x18002f19e  lea     rcx, _GUID_7b7166ec_21c7_44ae_b21a_c9ae321ae369; riid
0x18002f1a5  call    cs:__imp_CreateDXGIFactory
0x18002f1ac  nop     dword ptr [rax+rax+00h]
0x18002f1b1  test    eax, eax
0x18002f1b3  js      loc_18002F2BA
0x18002f1b9  mov     rcx, [rbp+57h+ppFactory]
0x18002f1bd  mov     rax, [rcx]
0x18002f1c0  lea     r8, [rbp+57h+var_A0]
0x18002f1c4  mov     edx, r14d
0x18002f1c7  mov     rax, [rax+38h]
0x18002f1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d0  mov     ebx, eax
0x18002f1d2  test    eax, eax
0x18002f1d4  js      loc_18002F266
0x18002f1da  mov     rcx, [rbp+57h+var_A0]
0x18002f1de  mov     rax, [rcx]
0x18002f1e1  lea     r8, [rbp+57h+var_98]
0x18002f1e5  xor     edx, edx
0x18002f1e7  mov     rax, [rax+38h]
0x18002f1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1f0  mov     ebx, eax
0x18002f1f2  test    eax, eax
0x18002f1f4  js      short loc_18002F266
0x18002f1f6  mov     rcx, [rbp+57h+var_98]
0x18002f1fa  mov     rax, [rcx]
0x18002f1fd  lea     rdx, [rbp+57h+var_80]
0x18002f201  mov     rax, [rax+38h]
0x18002f205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f20a  mov     ebx, eax
0x18002f20c  test    eax, eax
0x18002f20e  js      short loc_18002F266
0x18002f210  cmp     [rbp+57h+var_30], 0
0x18002f214  jz      short loc_18002F222
0x18002f216  cmp     [rbp+57h+var_3C], 0
0x18002f21a  jnz     short loc_18002F222
0x18002f21c  cmp     [rbp+57h+var_40], 0
0x18002f220  jz      short loc_18002F254
0x18002f222  mov     rcx, [rbp+57h+var_98]
0x18002f226  mov     rax, [rcx]
0x18002f229  mov     rax, [rax+10h]
0x18002f22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f232  and     [rbp+57h+var_98], 0
0x18002f237  mov     rcx, [rbp+57h+var_A0]
0x18002f23b  mov     rax, [rcx]
0x18002f23e  mov     rax, [rax+10h]
0x18002f242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f247  and     [rbp+57h+var_A0], 0
0x18002f24c  inc     r14d
0x18002f24f  jmp     loc_18002F1B9
0x18002f254  mov     rax, [rbp+57h+var_A0]
0x18002f258  mov     [rdi], rax
0x18002f25b  xor     ecx, ecx
0x18002f25d  mov     [rbp+57h+var_A0], rcx
0x18002f261  mov     sil, 1
0x18002f264  jmp     short loc_18002F26A
0x18002f266  mov     rcx, [rbp+57h+var_A0]
0x18002f26a  test    rcx, rcx
0x18002f26d  jz      short loc_18002F280
0x18002f26f  mov     rax, [rcx]
0x18002f272  mov     rax, [rax+10h]
0x18002f276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f27b  and     [rbp+57h+var_A0], 0
0x18002f280  mov     rcx, [rbp+57h+var_98]
0x18002f284  test    rcx, rcx
0x18002f287  jz      short loc_18002F29A
0x18002f289  mov     rax, [rcx]
0x18002f28c  mov     rax, [rax+10h]
0x18002f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f295  and     [rbp+57h+var_98], 0
0x18002f29a  mov     rcx, [rbp+57h+ppFactory]
0x18002f29e  test    rcx, rcx
0x18002f2a1  jz      short loc_18002F2AF
0x18002f2a3  mov     rax, [rcx]
0x18002f2a6  mov     rax, [rax+10h]
0x18002f2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2af  test    sil, sil
0x18002f2b2  jnz     short loc_18002F2B8
0x18002f2b4  and     qword ptr [rdi], 0
0x18002f2b8  mov     eax, ebx
0x18002f2ba  mov     rcx, [rbp+57h+var_20]
0x18002f2be  xor     rcx, rsp; StackCookie
0x18002f2c1  call    __security_check_cookie
0x18002f2c6  lea     r11, [rsp+0C0h+var_10]
0x18002f2ce  mov     rbx, [r11+28h]
0x18002f2d2  mov     rsi, [r11+30h]
0x18002f2d6  mov     rsp, r11
0x18002f2d9  pop     r14
0x18002f2db  pop     rdi
0x18002f2dc  pop     rbp
0x18002f2dd  retn
```
