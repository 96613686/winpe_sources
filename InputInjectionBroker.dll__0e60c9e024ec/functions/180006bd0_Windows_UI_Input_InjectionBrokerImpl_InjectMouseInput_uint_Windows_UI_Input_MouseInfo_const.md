# Windows::UI::Input::InjectionBrokerImpl::InjectMouseInput(uint,Windows::UI::Input::MouseInfo * const)

- ea: `0x180006bd0`
- end: `0x180006cf7`
- name: `?InjectMouseInput@InjectionBrokerImpl@Input@UI@Windows@@UEAAJIQEAUMouseInfo@234@@Z`
- size: `295`
- prototype: `__int64 __fastcall(Windows::UI::Input::InjectionBrokerImpl *__hidden this, unsigned int, struct Windows::UI::Input::MouseInfo *const)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006bd0`
- `0x18000ee6c`
- `0x18001143a`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cd5`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectMouseInput` at `0x180006cb3`
- `ext-ms-win-ntuser-rim-l1-1-0!InjectMouseInput` at `0x180006cb3`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::InjectMouseInput(
        Windows::UI::Input::InjectionBrokerImpl *this,
        unsigned int a2,
        struct Windows::UI::Input::MouseInfo *const a3)
{
  unsigned int *v3; // rbp
  unsigned __int64 v4; // rsi
  signed int v6; // ebx
  unsigned int *v7; // rdi
  unsigned int *v8; // rdx
  unsigned int v9; // r9d
  unsigned __int128 v10; // rax
  int v11; // eax
  __int64 v12; // r10
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  signed int LastError; // eax
  void *pv; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v19[4]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v20; // [rsp+40h] [rbp-58h]

  v3 = 0;
  v4 = a2;
  pv = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  if ( a2 == 1 )
  {
    v6 = 0;
    v7 = v19;
    v8 = v19;
    v9 = 0;
LABEL_8:
    v12 = 0;
    do
    {
      v13 = 5 * v12;
      v14 = *((_DWORD *)a3 + 5 * v12 + 3);
      ++v9;
      v15 = 8 * v12++;
      v8[v15 + 3] = v14;
      v8[v15] = *((_DWORD *)a3 + v13);
      v8[v15 + 1] = *((_DWORD *)a3 + v13 + 1);
      v8[v15 + 2] = *((_DWORD *)a3 + v13 + 2);
      v8[v15 + 4] = *((_DWORD *)a3 + v13 + 4);
    }
    while ( v9 < (unsigned int)v4 );
LABEL_10:
    if ( !(unsigned int)InjectMouseInput(v7, (unsigned int)v4) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_13;
  }
  v10 = a2 * (unsigned __int128)0x20uLL;
  if ( is_mul_ok(v4, 0x20u) )
  {
    v11 = CTCoAllocPolicy::Alloc(this, DWORD2(v10), 32 * v4, &pv);
    v3 = (unsigned int *)pv;
    v6 = v11;
  }
  else
  {
    v6 = -2147024362;
  }
  if ( v6 >= 0 )
  {
    v7 = v3;
    memset_0(v3, 0, 32 * v4);
    v9 = 0;
    v8 = v3;
    if ( !(_DWORD)v4 )
      goto LABEL_10;
    goto LABEL_8;
  }
LABEL_13:
  CoTaskMemFree(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006bd0  push    rbx
0x180006bd2  push    rbp
0x180006bd3  push    rsi
0x180006bd4  push    rdi
0x180006bd5  push    r14
0x180006bd7  push    r15
0x180006bd9  sub     rsp, 68h
0x180006bdd  mov     rax, cs:__security_cookie
0x180006be4  xor     rax, rsp
0x180006be7  mov     [rsp+98h+var_48], rax
0x180006bec  xor     ebp, ebp
0x180006bee  mov     esi, edx
0x180006bf0  mov     [rsp+98h+pv], rbp
0x180006bf5  xorps   xmm0, xmm0
0x180006bf8  mov     r15, r8
0x180006bfb  movups  xmmword ptr [rsp+98h+var_68], xmm0
0x180006c00  movups  [rsp+98h+var_58], xmm0
0x180006c05  cmp     edx, 1
0x180006c08  jnz     short loc_180006C19
0x180006c0a  xor     ebx, ebx
0x180006c0c  lea     rdi, [rsp+98h+var_68]
0x180006c11  mov     rdx, rdi; unsigned int
0x180006c14  xor     r9d, r9d
0x180006c17  jmp     short loc_180006C6A
0x180006c19  mov     eax, 20h ; ' '
0x180006c1e  mov     r14, rsi
0x180006c21  mul     rsi
0x180006c24  test    rdx, rdx
0x180006c27  jnz     short loc_180006C3F
0x180006c29  lea     r9, [rsp+98h+pv]; void **
0x180006c2e  mov     r8, rax; unsigned __int64
0x180006c31  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180006c36  mov     rbp, [rsp+98h+pv]
0x180006c3b  mov     ebx, eax
0x180006c3d  jmp     short loc_180006C44
0x180006c3f  mov     ebx, 80070216h
0x180006c44  test    ebx, ebx
0x180006c46  js      loc_180006CD2
0x180006c4c  shl     r14, 5
0x180006c50  xor     edx, edx; Val
0x180006c52  mov     r8, r14; Size
0x180006c55  mov     rcx, rbp; void *
0x180006c58  mov     rdi, rbp
0x180006c5b  call    memset_0
0x180006c60  xor     r9d, r9d
0x180006c63  mov     rdx, rbp
0x180006c66  test    esi, esi
0x180006c68  jz      short loc_180006CAE
0x180006c6a  xor     r10d, r10d
0x180006c6d  lea     r8, [r10+r10*4]
0x180006c71  mov     rcx, r10
0x180006c74  mov     eax, [r15+r8*4+0Ch]
0x180006c79  inc     r9d
0x180006c7c  shl     rcx, 5
0x180006c80  inc     r10
0x180006c83  mov     [rcx+rdx+0Ch], eax
0x180006c87  mov     eax, [r15+r8*4]
0x180006c8b  mov     [rcx+rdx], eax
0x180006c8e  mov     eax, [r15+r8*4+4]
0x180006c93  mov     [rcx+rdx+4], eax
0x180006c97  mov     eax, [r15+r8*4+8]
0x180006c9c  mov     [rcx+rdx+8], eax
0x180006ca0  mov     eax, [r15+r8*4+10h]
0x180006ca5  mov     [rcx+rdx+10h], eax
0x180006ca9  cmp     r9d, esi
0x180006cac  jb      short loc_180006C6D
0x180006cae  mov     edx, esi
0x180006cb0  mov     rcx, rdi
0x180006cb3  call    cs:__imp_InjectMouseInput
0x180006cb9  test    eax, eax
0x180006cbb  jnz     short loc_180006CD2
0x180006cbd  call    cs:__imp_GetLastError
0x180006cc3  mov     ebx, eax
0x180006cc5  test    eax, eax
0x180006cc7  jle     short loc_180006CD2
0x180006cc9  movzx   ebx, ax
0x180006ccc  or      ebx, 80070000h
0x180006cd2  mov     rcx, rbp; pv
0x180006cd5  call    cs:__imp_CoTaskMemFree
0x180006cdb  mov     eax, ebx
0x180006cdd  mov     rcx, [rsp+98h+var_48]
0x180006ce2  xor     rcx, rsp; StackCookie
0x180006ce5  call    __security_check_cookie
0x180006cea  add     rsp, 68h
0x180006cee  pop     r15
0x180006cf0  pop     r14
0x180006cf2  pop     rdi
0x180006cf3  pop     rsi
0x180006cf4  pop     rbp
0x180006cf5  pop     rbx
0x180006cf6  retn
```
