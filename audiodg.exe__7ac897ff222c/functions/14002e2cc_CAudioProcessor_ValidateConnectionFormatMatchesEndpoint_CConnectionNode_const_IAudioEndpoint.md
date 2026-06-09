# CAudioProcessor::ValidateConnectionFormatMatchesEndpoint(CConnectionNode const &,IAudioEndpoint *)

- ea: `0x14002e2cc`
- end: `0x14002e419`
- name: `?ValidateConnectionFormatMatchesEndpoint@CAudioProcessor@@AEAAJAEBVCConnectionNode@@PEAUIAudioEndpoint@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CAudioProcessor *__hidden this, const struct CConnectionNode *, struct IAudioEndpoint *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14006c344`

## callees

- `0x14000a378`
- `0x14000c33c`
- `0x14002e2cc`
- `0x14002e420`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e3e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002e3e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAudioProcessor::ValidateConnectionFormatMatchesEndpoint(
        CAudioProcessor *this,
        const struct CConnectionNode *a2,
        struct IAudioEndpoint *a3)
{
  struct IAudioEndpointVtbl *lpVtbl; // rax
  int v5; // edi
  void *v6; // rcx
  int *v7; // rcx
  __int16 v8; // ax
  void *v10; // rcx
  void *v11; // [rsp+28h] [rbp-18h] BYREF
  char v12; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  LPVOID pv; // [rsp+50h] [rbp+10h] BYREF

  pv = 0;
  lpVtbl = a3->lpVtbl;
  v11 = 0;
  v12 = 1;
  v5 = ((__int64 (__fastcall *)(struct IAudioEndpoint *, void **))lpVtbl->GetFrameFormat)(a3, &v11);
  if ( v12 )
  {
    v6 = pv;
    pv = v11;
    if ( v6 )
      CoTaskMemFree(v6);
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89E,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
      (const char *)(unsigned int)v5,
      (int)&pv);
    v10 = pv;
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
    return (unsigned int)v5;
  }
  else
  {
    if ( *((unsigned __int16 *)pv + 7) >> 3 != *((_DWORD *)a2 + 19)
      || *((unsigned __int16 *)pv + 1) != *((_DWORD *)a2 + 18)
      || GetBitsPerSample((const struct tWAVEFORMATEX *)pv) != *((_DWORD *)a2 + 20)
      || (float)v7[1] != *((float *)a2 + 21) )
    {
      goto LABEL_18;
    }
    v8 = *(_WORD *)v7;
    if ( *(_WORD *)v7 == 0xFFFE )
      v8 = *((_WORD *)v7 + 12);
    if ( v8 == *((_WORD *)a2 + 28) )
    {
      pv = 0;
      if ( v7 )
        CoTaskMemFree(v7);
      return 0;
    }
    else
    {
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A5,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioprocessor.cpp",
        (const char *)0x887C001ELL,
        (int)&pv);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pv,
        0);
      return 2289827870LL;
    }
  }
}

```

## disassembly

```asm
0x14002e2cc  mov     [rsp-8+arg_8], rbx
0x14002e2d1  mov     [rsp-8+arg_10], rdi
0x14002e2d6  mov     [rsp-8+pv], rcx
0x14002e2db  push    rbp
0x14002e2dc  mov     rbp, rsp
0x14002e2df  sub     rsp, 40h
0x14002e2e3  mov     rbx, rdx
0x14002e2e6  mov     [rbp+pv], 0
0x14002e2ee  mov     rax, [r8]
0x14002e2f1  lea     rcx, [rbp+pv]
0x14002e2f5  mov     [rbp+var_20], rcx
0x14002e2f9  mov     [rbp+var_18], 0
0x14002e301  mov     [rbp+var_10], 1
0x14002e305  lea     rdx, [rbp+var_18]
0x14002e309  mov     rcx, r8
0x14002e30c  mov     rax, [rax+18h]
0x14002e310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e315  mov     edi, eax
0x14002e317  cmp     [rbp+var_10], 0
0x14002e31b  jz      short loc_14002E336
0x14002e31d  mov     r8, [rbp+var_20]
0x14002e321  mov     rcx, [r8]; pv
0x14002e324  mov     rdx, [rbp+var_18]
0x14002e328  mov     [r8], rdx
0x14002e32b  test    rcx, rcx
0x14002e32e  jz      short loc_14002E336
0x14002e330  call    cs:__imp_CoTaskMemFree
0x14002e336  test    edi, edi
0x14002e338  js      short loc_14002E3B8
0x14002e33a  mov     rcx, [rbp+pv]; struct tWAVEFORMATEX *
0x14002e33e  movzx   eax, word ptr [rcx+0Eh]
0x14002e342  shr     eax, 3
0x14002e345  cmp     eax, [rbx+4Ch]
0x14002e348  jnz     loc_14002E3EC
0x14002e34e  movzx   eax, word ptr [rcx+2]
0x14002e352  cmp     eax, [rbx+48h]
0x14002e355  jnz     loc_14002E3EC
0x14002e35b  call    ?GetBitsPerSample@@YAIPEBUtWAVEFORMATEX@@@Z; GetBitsPerSample(tWAVEFORMATEX const *)
0x14002e360  cmp     eax, [rbx+50h]
0x14002e363  jnz     loc_14002E3EC
0x14002e369  mov     eax, [rcx+4]
0x14002e36c  xorps   xmm0, xmm0
0x14002e36f  cvtsi2ss xmm0, rax
0x14002e374  ucomiss xmm0, dword ptr [rbx+54h]
0x14002e378  jp      short loc_14002E3EC
0x14002e37a  jnz     short loc_14002E3EC
0x14002e37c  movzx   eax, word ptr [rcx]
0x14002e37f  mov     edx, 0FFFEh
0x14002e384  cmp     dx, ax
0x14002e387  jnz     short loc_14002E38D
0x14002e389  movzx   eax, word ptr [rcx+18h]
0x14002e38d  cmp     ax, [rbx+38h]
0x14002e391  jnz     short loc_14002E3EC
0x14002e393  mov     [rbp+pv], 0
0x14002e39b  test    rcx, rcx
0x14002e39e  jz      short loc_14002E3A6
0x14002e3a0  call    cs:__imp_CoTaskMemFree
0x14002e3a6  xor     eax, eax
0x14002e3a8  mov     rbx, [rsp+40h+arg_8]
0x14002e3ad  mov     rdi, [rsp+40h+arg_10]
0x14002e3b2  add     rsp, 40h
0x14002e3b6  pop     rbp
0x14002e3b7  retn
0x14002e3b8  mov     rcx, [rbp+8]; this
0x14002e3bc  mov     r9d, edi; char *
0x14002e3bf  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14002e3c6  mov     edx, 89Eh; void *
0x14002e3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e3d0  nop
0x14002e3d1  mov     rcx, [rbp+pv]; pv
0x14002e3d5  mov     [rbp+pv], 0
0x14002e3dd  test    rcx, rcx
0x14002e3e0  jz      short loc_14002E3E8
0x14002e3e2  call    cs:__imp_CoTaskMemFree
0x14002e3e8  mov     eax, edi
0x14002e3ea  jmp     short loc_14002E3A8
0x14002e3ec  mov     rcx, [rbp+8]; this
0x14002e3f0  mov     ebx, 887C001Eh
0x14002e3f5  mov     r9d, ebx; char *
0x14002e3f8  lea     r8, aAvcoreAudiocor_83; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14002e3ff  mov     edx, 8A5h; void *
0x14002e404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002e409  nop
0x14002e40a  xor     edx, edx
0x14002e40c  lea     rcx, [rbp+pv]
0x14002e410  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x14002e415  mov     eax, ebx
0x14002e417  jmp     short loc_14002E3A8
```
