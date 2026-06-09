# GetUevStatus(bool *,bool *)

- ea: `0x14000b1c4`
- end: `0x14000b2da`
- name: `?GetUevStatus@@YAXPEA_N0@Z`
- size: `278`
- prototype: `void __fastcall(bool *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b2e0`

## callees

- `0x140003e50`
- `0x14000b1c4`
- `0x14009b010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x14000b1f6`
- `ole32!CoInitializeEx` at `0x14000b1f6`
- `ole32!CoUninitialize` at `0x14000b2b1`
- `ole32!CoUninitialize` at `0x14000b2b1`
- `ole32!CoCreateInstance` at `0x14000b22d`
- `ole32!CoCreateInstance` at `0x14000b22d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GetUevStatus(bool *a1, bool *a2)
{
  HRESULT v4; // ebx
  bool v5; // di
  bool v6; // al
  _WORD v7[2]; // [rsp+34h] [rbp-34h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-30h] BYREF

  *a1 = 0;
  *a2 = 0;
  v4 = CoInitializeEx(0, 0);
  ppv = 0;
  v5 = 1;
  if ( CoCreateInstance(
         &GUID_4d4d7fab_11cf_4314_af4f_b84e96791cef,
         0,
         1u,
         &GUID_2b478abb_f15e_4d52_9ea7_48d702b6c20e,
         &ppv) >= 0 )
  {
    v7[0] = 0;
    v6 = (*(int (__fastcall **)(LPVOID, _WORD *))(*(_QWORD *)ppv + 40LL))(ppv, v7) >= 0 && v7[0] == 0xFFFF;
    *a1 = v6;
    if ( (*(int (__fastcall **)(LPVOID, _WORD *))(*(_QWORD *)ppv + 48LL))(ppv, v7) < 0 || v7[0] != 0xFFFF )
      v5 = 0;
    *a2 = v5;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x14000b1c4  mov     [rsp+arg_10], rbx
0x14000b1c9  mov     [rsp+arg_18], rsi
0x14000b1ce  push    rdi
0x14000b1cf  push    r14
0x14000b1d1  push    r15
0x14000b1d3  sub     rsp, 50h
0x14000b1d7  mov     rax, cs:__security_cookie
0x14000b1de  xor     rax, rsp
0x14000b1e1  mov     [rsp+68h+var_28], rax
0x14000b1e6  mov     rsi, rdx
0x14000b1e9  mov     r14, rcx
0x14000b1ec  mov     byte ptr [rcx], 0
0x14000b1ef  mov     byte ptr [rdx], 0
0x14000b1f2  xor     edx, edx; dwCoInit
0x14000b1f4  xor     ecx, ecx; pvReserved
0x14000b1f6  call    cs:__imp_CoInitializeEx
0x14000b1fc  mov     ebx, eax
0x14000b1fe  mov     [rsp+68h+var_38], eax
0x14000b202  mov     [rsp+68h+var_30], 0
0x14000b20b  lea     rax, [rsp+68h+var_30]
0x14000b210  mov     [rsp+68h+ppv], rax; ppv
0x14000b215  lea     r9, _GUID_2b478abb_f15e_4d52_9ea7_48d702b6c20e; riid
0x14000b21c  mov     edi, 1
0x14000b221  mov     r8d, edi; dwClsContext
0x14000b224  xor     edx, edx; pUnkOuter
0x14000b226  lea     rcx, _GUID_4d4d7fab_11cf_4314_af4f_b84e96791cef; rclsid
0x14000b22d  call    cs:__imp_CoCreateInstance
0x14000b233  test    eax, eax
0x14000b235  js      short loc_14000B296
0x14000b237  xor     eax, eax
0x14000b239  mov     [rsp+68h+var_34], ax
0x14000b23e  mov     rcx, [rsp+68h+var_30]
0x14000b243  mov     rax, [rcx]
0x14000b246  lea     rdx, [rsp+68h+var_34]
0x14000b24b  mov     rax, [rax+28h]
0x14000b24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b254  or      r15d, 0FFFFFFFFh
0x14000b258  test    eax, eax
0x14000b25a  js      short loc_14000B269
0x14000b25c  cmp     r15w, [rsp+68h+var_34]
0x14000b262  jnz     short loc_14000B269
0x14000b264  mov     al, dil
0x14000b267  jmp     short loc_14000B26B
0x14000b269  xor     al, al
0x14000b26b  mov     [r14], al
0x14000b26e  mov     rcx, [rsp+68h+var_30]
0x14000b273  mov     rax, [rcx]
0x14000b276  lea     rdx, [rsp+68h+var_34]
0x14000b27b  mov     rax, [rax+30h]
0x14000b27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b284  test    eax, eax
0x14000b286  js      short loc_14000B290
0x14000b288  cmp     r15w, [rsp+68h+var_34]
0x14000b28e  jz      short loc_14000B293
0x14000b290  xor     dil, dil
0x14000b293  mov     [rsi], dil
0x14000b296  mov     rcx, [rsp+68h+var_30]
0x14000b29b  test    rcx, rcx
0x14000b29e  jz      short loc_14000B2AD
0x14000b2a0  mov     rax, [rcx]
0x14000b2a3  mov     rax, [rax+10h]
0x14000b2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2ac  nop
0x14000b2ad  test    ebx, ebx
0x14000b2af  js      short loc_14000B2B7
0x14000b2b1  call    cs:__imp_CoUninitialize
0x14000b2b7  mov     rcx, [rsp+68h+var_28]
0x14000b2bc  xor     rcx, rsp; StackCookie
0x14000b2bf  call    __security_check_cookie
0x14000b2c4  lea     r11, [rsp+68h+var_18]
0x14000b2c9  mov     rbx, [r11+30h]
0x14000b2cd  mov     rsi, [r11+38h]
0x14000b2d1  mov     rsp, r11
0x14000b2d4  pop     r15
0x14000b2d6  pop     r14
0x14000b2d8  pop     rdi
0x14000b2d9  retn
```
