# Windows::UI::Input::InjectionBrokerImpl::InjectKeyboardInput(uint,Windows::UI::Input::KeyboardInfo * const)

- ea: `0x180006a90`
- end: `0x180006bc0`
- name: `?InjectKeyboardInput@InjectionBrokerImpl@Input@UI@Windows@@UEAAJIQEAUKeyboardInfo@234@@Z`
- size: `304`
- prototype: `__int64 __fastcall(Windows::UI::Input::InjectionBrokerImpl *__hidden this, unsigned int, struct Windows::UI::Input::KeyboardInfo *const)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006a90`
- `0x18000ee6c`
- `0x18001143a`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b95`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectKeyboardInput` at `0x180006b6c`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectKeyboardInput` at `0x180006b6c`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::InjectKeyboardInput(
        Windows::UI::Input::InjectionBrokerImpl *this,
        unsigned int a2,
        struct Windows::UI::Input::KeyboardInfo *const a3)
{
  __int128 *v3; // rdi
  unsigned __int64 v4; // rsi
  __int128 *v6; // r9
  unsigned int v7; // ebx
  __int128 *v8; // rdx
  unsigned int v9; // r11d
  unsigned __int128 v10; // rax
  int v11; // eax
  __int64 v12; // r10
  __int64 v13; // r8
  __int64 v14; // rcx
  signed int LastError; // eax
  void *pv; // [rsp+20h] [rbp-48h] BYREF
  __int128 v18; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h]

  v3 = 0;
  v4 = a2;
  pv = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 == 1 )
  {
    v6 = &v18;
    v7 = 0;
    v8 = &v18;
    v9 = 0;
LABEL_6:
    v12 = 0;
    do
    {
      v13 = 3 * v12;
      ++v9;
      v14 = 3 * v12;
      *((_DWORD *)v8 + 2 * v14 + 1) = *((_DWORD *)a3 + 3 * v12++ + 1);
      *((_DWORD *)v8 + 2 * v14 + 2) = *((_DWORD *)a3 + v13 + 2);
      *((_WORD *)v8 + 4 * v14 + 1) = *((_WORD *)a3 + 2 * v13 + 1);
      *((_WORD *)v8 + 4 * v14) = *((_WORD *)a3 + 2 * v13);
    }
    while ( v9 < (unsigned int)v4 );
LABEL_8:
    if ( !(unsigned int)InjectKeyboardInput(v6, (unsigned int)v4) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_12;
  }
  v10 = a2 * (unsigned __int128)0x18uLL;
  if ( !is_mul_ok(v4, 0x18u) )
  {
    v7 = -2147024362;
    goto LABEL_12;
  }
  v11 = CTCoAllocPolicy::Alloc(this, DWORD2(v10), 24 * v4, &pv);
  v3 = (__int128 *)pv;
  v7 = v11;
  if ( v11 >= 0 )
  {
    memset_0(pv, 0, 24 * v4);
    v9 = 0;
    v6 = v3;
    v8 = v3;
    if ( !(_DWORD)v4 )
      goto LABEL_8;
    goto LABEL_6;
  }
LABEL_12:
  CoTaskMemFree(v3);
  return v7;
}

```

## disassembly

```asm
0x180006a90  mov     r11, rsp
0x180006a93  mov     [r11+8], rbx
0x180006a97  mov     [r11+18h], rsi
0x180006a9b  push    rdi
0x180006a9c  push    r14
0x180006a9e  push    r15
0x180006aa0  sub     rsp, 50h
0x180006aa4  mov     rax, cs:__security_cookie
0x180006aab  xor     rax, rsp
0x180006aae  mov     [rsp+68h+var_20], rax
0x180006ab3  xor     edi, edi
0x180006ab5  mov     esi, edx
0x180006ab7  xor     eax, eax
0x180006ab9  mov     [r11-48h], rdi
0x180006abd  xorps   xmm0, xmm0
0x180006ac0  mov     r15, r8
0x180006ac3  movups  [rsp+68h+var_38], xmm0
0x180006ac8  mov     [r11-28h], rax
0x180006acc  cmp     edx, 1
0x180006acf  jnz     short loc_180006ADF
0x180006ad1  lea     r9, [r11-38h]
0x180006ad5  xor     ebx, ebx
0x180006ad7  mov     rdx, r9; unsigned int
0x180006ada  xor     r11d, r11d
0x180006add  jmp     short loc_180006B2B
0x180006adf  mov     eax, 18h
0x180006ae4  mul     rsi
0x180006ae7  test    rdx, rdx
0x180006aea  jnz     loc_180006B8D
0x180006af0  lea     r9, [rsp+68h+pv]; void **
0x180006af5  mov     r8, rax; unsigned __int64
0x180006af8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180006afd  mov     rdi, [rsp+68h+pv]
0x180006b02  mov     ebx, eax
0x180006b04  test    eax, eax
0x180006b06  js      loc_180006B92
0x180006b0c  lea     r8, [rsi+rsi*2]
0x180006b10  xor     edx, edx; Val
0x180006b12  shl     r8, 3; Size
0x180006b16  mov     rcx, rdi; void *
0x180006b19  call    memset_0
0x180006b1e  xor     r11d, r11d
0x180006b21  mov     r9, rdi
0x180006b24  mov     rdx, rdi
0x180006b27  test    esi, esi
0x180006b29  jz      short loc_180006B67
0x180006b2b  xor     r10d, r10d
0x180006b2e  lea     r8, [r10+r10*2]
0x180006b32  inc     r11d
0x180006b35  mov     eax, [r15+r8*4+4]
0x180006b3a  lea     rcx, [r10+r10*2]
0x180006b3e  mov     [rdx+rcx*8+4], eax
0x180006b42  inc     r10
0x180006b45  mov     eax, [r15+r8*4+8]
0x180006b4a  mov     [rdx+rcx*8+8], eax
0x180006b4e  movzx   eax, word ptr [r15+r8*4+2]
0x180006b54  mov     [rdx+rcx*8+2], ax
0x180006b59  movzx   eax, word ptr [r15+r8*4]
0x180006b5e  mov     [rdx+rcx*8], ax
0x180006b62  cmp     r11d, esi
0x180006b65  jb      short loc_180006B2E
0x180006b67  mov     edx, esi
0x180006b69  mov     rcx, r9
0x180006b6c  call    cs:__imp_InjectKeyboardInput
0x180006b72  test    eax, eax
0x180006b74  jnz     short loc_180006B92
0x180006b76  call    cs:__imp_GetLastError
0x180006b7c  mov     ebx, eax
0x180006b7e  test    eax, eax
0x180006b80  jle     short loc_180006B92
0x180006b82  movzx   ebx, ax
0x180006b85  or      ebx, 80070000h
0x180006b8b  jmp     short loc_180006B92
0x180006b8d  mov     ebx, 80070216h
0x180006b92  mov     rcx, rdi; pv
0x180006b95  call    cs:__imp_CoTaskMemFree
0x180006b9b  mov     eax, ebx
0x180006b9d  mov     rcx, [rsp+68h+var_20]
0x180006ba2  xor     rcx, rsp; StackCookie
0x180006ba5  call    __security_check_cookie
0x180006baa  lea     r11, [rsp+68h+var_18]
0x180006baf  mov     rbx, [r11+20h]
0x180006bb3  mov     rsi, [r11+30h]
0x180006bb7  mov     rsp, r11
0x180006bba  pop     r15
0x180006bbc  pop     r14
0x180006bbe  pop     rdi
0x180006bbf  retn
```
