# SmartActivationContext::SmartActivationContext(std::filesystem::path,std::filesystem::path)

- ea: `0x1800361a8`
- end: `0x180036307`
- name: `??0SmartActivationContext@@QEAA@Vpath@filesystem@std@@0@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180038ef0`

## callees

- `0x180026a00`
- `0x180028728`
- `0x180029644`
- `0x1800361a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003626d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003626d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036280`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036280`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180036278`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180036278`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800362ab`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800362ab`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180036252`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180036252`

## pseudocode

```c
__int64 __fastcall SmartActivationContext::SmartActivationContext(__int64 a1, __int64 a2, __int64 a3)
{
  ACTCTXW *v6; // r14
  _QWORD *v7; // rbx
  _QWORD *v8; // rsi
  char *ActCtxW; // rsi
  const char *v10; // r9
  void *v11; // rbp
  DWORD LastError; // ebx
  BOOL v13; // eax
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)a1 = &SmartActivationContext::`vftable';
  v6 = (ACTCTXW *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 24) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v7 = (_QWORD *)(a1 + 64);
  std::wstring::wstring(a1 + 64, a2);
  v8 = (_QWORD *)(a1 + 96);
  std::wstring::wstring(a1 + 96, a3);
  *(_QWORD *)(a1 + 128) = -1;
  *(_DWORD *)(a1 + 136) = 0;
  v6->cbSize = 56;
  *(_DWORD *)(a1 + 12) = 4;
  if ( *(_QWORD *)(a1 + 120) > 7u )
    v8 = (_QWORD *)*v8;
  *(_QWORD *)(a1 + 16) = v8;
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  *(_QWORD *)(a1 + 32) = v7;
  ActCtxW = (char *)CreateActCtxW(v6);
  v11 = *(void **)(a1 + 128);
  if ( v11 != (void *)-1LL && v11 )
  {
    LastError = GetLastError();
    ReleaseActCtx(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 128) = ActCtxW;
  if ( (unsigned __int64)(ActCtxW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x12,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\SmartActivationContext.hpp",
      v10);
  v13 = ActivateActCtx(ActCtxW, (ULONG_PTR *)(a1 + 144));
  *(_DWORD *)(a1 + 136) = v13;
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\SmartActivationContext.hpp",
      v14);
  std::wstring::_Tidy_deallocate(a2);
  std::wstring::_Tidy_deallocate(a3);
  return a1;
}

```

## disassembly

```asm
0x1800361a8  mov     [rsp+arg_10], r8
0x1800361ad  mov     [rsp+arg_8], rdx
0x1800361b2  mov     [rsp+arg_0], rcx
0x1800361b7  push    rbx
0x1800361b8  push    rbp
0x1800361b9  push    rsi
0x1800361ba  push    rdi
0x1800361bb  push    r12
0x1800361bd  push    r14
0x1800361bf  push    r15
0x1800361c1  sub     rsp, 20h
0x1800361c5  mov     r15, r8
0x1800361c8  mov     r12, rdx
0x1800361cb  mov     rdi, rcx
0x1800361ce  lea     rax, ??_7SmartActivationContext@@6B@; const SmartActivationContext::`vftable'
0x1800361d5  mov     [rcx], rax
0x1800361d8  lea     r14, [rcx+8]
0x1800361dc  xorps   xmm0, xmm0
0x1800361df  xor     eax, eax
0x1800361e1  movups  xmmword ptr [r14], xmm0
0x1800361e5  movups  xmmword ptr [r14+10h], xmm0
0x1800361ea  movups  xmmword ptr [r14+20h], xmm0
0x1800361ef  mov     [r14+30h], rax
0x1800361f3  lea     rbx, [rcx+40h]
0x1800361f7  mov     rcx, rbx
0x1800361fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800361ff  nop
0x180036200  lea     rsi, [rdi+60h]
0x180036204  mov     rdx, r15
0x180036207  mov     rcx, rsi
0x18003620a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003620f  nop
0x180036210  mov     qword ptr [rdi+80h], 0FFFFFFFFFFFFFFFFh
0x18003621b  mov     dword ptr [rdi+88h], 0
0x180036225  mov     dword ptr [r14], 38h ; '8'
0x18003622c  mov     dword ptr [rdi+0Ch], 4
0x180036233  cmp     qword ptr [rsi+18h], 7
0x180036238  jbe     short loc_18003623D
0x18003623a  mov     rsi, [rsi]
0x18003623d  mov     [rdi+10h], rsi
0x180036241  cmp     qword ptr [rbx+18h], 7
0x180036246  jbe     short loc_18003624B
0x180036248  mov     rbx, [rbx]
0x18003624b  mov     [rdi+20h], rbx
0x18003624f  mov     rcx, r14; pActCtx
0x180036252  call    cs:__imp_CreateActCtxW
0x180036258  mov     rsi, rax
0x18003625b  mov     rbp, [rdi+80h]
0x180036262  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180036266  jz      short loc_180036286
0x180036268  test    rbp, rbp
0x18003626b  jz      short loc_180036286
0x18003626d  call    cs:__imp_GetLastError
0x180036273  mov     ebx, eax
0x180036275  mov     rcx, rbp; hActCtx
0x180036278  call    cs:__imp_ReleaseActCtx
0x18003627e  mov     ecx, ebx; dwErrCode
0x180036280  call    cs:__imp_SetLastError
0x180036286  mov     [rdi+80h], rsi
0x18003628d  lea     rax, [rsi-1]
0x180036291  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036295  setbe   al
0x180036298  mov     rcx, [rsp+58h]; this
0x18003629d  test    al, al
0x18003629f  jz      short loc_1800362F5
0x1800362a1  lea     rdx, [rdi+90h]; lpCookie
0x1800362a8  mov     rcx, rsi; hActCtx
0x1800362ab  call    cs:__imp_ActivateActCtx
0x1800362b1  mov     [rdi+88h], eax
0x1800362b7  mov     rcx, [rsp+58h]; this
0x1800362bc  test    eax, eax
0x1800362be  jz      short loc_1800362E3
0x1800362c0  mov     rcx, r12
0x1800362c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800362c8  nop
0x1800362c9  mov     rcx, r15
0x1800362cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800362d1  mov     rax, rdi
0x1800362d4  add     rsp, 20h
0x1800362d8  pop     r15
0x1800362da  pop     r14
0x1800362dc  pop     r12
0x1800362de  pop     rdi
0x1800362df  pop     rsi
0x1800362e0  pop     rbp
0x1800362e1  pop     rbx
0x1800362e2  retn
0x1800362e3  lea     r8, aCW1SSrcBrainLi_8; "C:\\__w\\1\\s\\src\\brain\\lib\\SmartAc"...
0x1800362ea  mov     edx, 18h; void *
0x1800362ef  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800362f5  lea     r8, aCW1SSrcBrainLi_8; "C:\\__w\\1\\s\\src\\brain\\lib\\SmartAc"...
0x1800362fc  mov     edx, 12h; void *
0x180036301  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
