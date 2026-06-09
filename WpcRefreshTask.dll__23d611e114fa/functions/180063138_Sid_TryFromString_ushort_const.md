# Sid::TryFromString(ushort const *)

- ea: `0x180063138`
- end: `0x180063350`
- name: `?TryFromString@Sid@@SA?AV?$Optional@VSid@@@@PEBG@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062974`

## callees

- `0x1800060a0`
- `0x180007ed9`
- `0x180009a80`
- `0x1800157f8`
- `0x18001f348`
- `0x180062344`
- `0x180063138`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063320`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006322a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006322a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063259`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063259`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800631b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800631b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Sid::TryFromString(__int64 a1, const WCHAR *a2)
{
  BOOL v4; // ebx
  _BYTE *v5; // rdx
  PSID v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  void **v9; // rdi
  __int64 v10; // rbx
  PSID pSourceSid; // [rsp+20h] [rbp-E0h] BYREF
  PSID v13[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v14[9]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD pDestinationSid[4]; // [rsp+90h] [rbp-70h] BYREF
  int v16; // [rsp+D0h] [rbp-30h]
  void *v17[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v19; // [rsp+F0h] [rbp-10h]
  PSID Sid; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v21[56]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE *v22; // [rsp+140h] [rbp+40h]

  v13[0] = (PSID)a1;
  if ( !a2 || !*a2 )
  {
    SetLastError(0x57u);
    *(_QWORD *)(a1 + 112) = 0;
    return a1;
  }
  pSourceSid = 0;
  v14[0] = &std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable';
  v14[1] = &pSourceSid;
  v14[7] = v14;
  stdext::GetPointer<void *>::GetPointer<void *>(&Sid, v14);
  v4 = ConvertStringSidToSidW(a2, &Sid);
  if ( v22 )
  {
    v13[0] = Sid;
    (*(void (__fastcall **)(_BYTE *, PSID *))(*(_QWORD *)v22 + 16LL))(v22, v13);
    if ( v22 )
    {
      v5 = v21;
      LOBYTE(v5) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v5);
    }
  }
  if ( v4 )
  {
    Sid::Sid((Sid *)pDestinationSid);
    if ( !CopySid(0x44u, pDestinationSid, pSourceSid) )
    {
      *(_QWORD *)(a1 + 112) = 0;
      std::wstring::~wstring(v17);
      v6 = pSourceSid;
      if ( !pSourceSid )
        return a1;
      goto LABEL_11;
    }
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( v8 > v19 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v17, v8, v7, a2);
    }
    else
    {
      v9 = v17;
      if ( v19 > 7 )
        v9 = (void **)v17[0];
      v18 = v8;
      v10 = 2 * v8;
      memmove_0(v9, a2, 2 * v8);
      *(_WORD *)((char *)v9 + v10) = 0;
    }
    *(_OWORD *)(a1 + 8) = pDestinationSid[0];
    *(_OWORD *)(a1 + 24) = pDestinationSid[1];
    *(_OWORD *)(a1 + 40) = pDestinationSid[2];
    *(_OWORD *)(a1 + 56) = pDestinationSid[3];
    *(_DWORD *)(a1 + 72) = v16;
    *(void **)(a1 + 80) = v17[0];
    *(void **)(a1 + 88) = v17[1];
    *(_QWORD *)(a1 + 96) = v18;
    *(_QWORD *)(a1 + 104) = v19;
    v18 = 0;
    v19 = 7;
    LOWORD(v17[0]) = 0;
    *(_QWORD *)(a1 + 112) = a1 + 8;
    std::wstring::~wstring(v17);
  }
  else
  {
    *(_QWORD *)(a1 + 112) = 0;
  }
  v6 = pSourceSid;
LABEL_11:
  if ( v6 )
    LocalFree(v6);
  return a1;
}

```

## disassembly

```asm
0x180063138  mov     [rsp-8+arg_10], rbx
0x18006313d  push    rbp
0x18006313e  push    rsi
0x18006313f  push    rdi
0x180063140  push    r14
0x180063142  push    r15
0x180063144  lea     rbp, [rsp-60h]
0x180063149  sub     rsp, 160h
0x180063150  mov     rax, cs:__security_cookie
0x180063157  xor     rax, rsp
0x18006315a  mov     [rbp+80h+var_30], rax
0x18006315e  mov     r14, rdx
0x180063161  mov     rsi, rcx
0x180063164  mov     [rsp+180h+var_150], rcx
0x180063169  xor     r15d, r15d
0x18006316c  test    rdx, rdx
0x18006316f  jz      loc_18006331B
0x180063175  cmp     [rdx], r15w
0x180063179  jz      loc_18006331B
0x18006317f  mov     [rsp+180h+pSourceSid], r15
0x180063184  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1a0a9a37411416c90e606832c1826ed5_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable'
0x18006318b  mov     [rsp+180h+var_138], rax
0x180063190  lea     rax, [rsp+180h+pSourceSid]
0x180063195  mov     [rsp+180h+var_130], rax
0x18006319a  lea     rax, [rsp+180h+var_138]
0x18006319f  mov     [rbp+80h+var_100], rax
0x1800631a3  lea     rdx, [rsp+180h+var_138]
0x1800631a8  lea     rcx, [rbp+80h+Sid]
0x1800631ac  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x1800631b1  lea     rdx, [rbp+80h+Sid]; Sid
0x1800631b5  mov     rcx, r14; StringSid
0x1800631b8  call    cs:__imp_ConvertStringSidToSidW
0x1800631be  mov     ebx, eax
0x1800631c0  mov     rcx, [rbp+80h+var_40]
0x1800631c4  test    rcx, rcx
0x1800631c7  jz      short loc_180063203
0x1800631c9  mov     rax, [rbp+80h+Sid]
0x1800631cd  mov     [rsp+180h+var_150], rax
0x1800631d2  mov     rax, [rcx]
0x1800631d5  lea     rdx, [rsp+180h+var_150]
0x1800631da  mov     rax, [rax+10h]
0x1800631de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631e3  mov     rcx, [rbp+80h+var_40]
0x1800631e7  test    rcx, rcx
0x1800631ea  jz      short loc_180063203
0x1800631ec  mov     rax, [rcx]
0x1800631ef  lea     rdx, [rbp+80h+var_78]
0x1800631f3  cmp     rcx, rdx
0x1800631f6  setnz   dl
0x1800631f9  mov     rax, [rax+20h]
0x1800631fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063202  nop
0x180063203  test    ebx, ebx
0x180063205  jnz     short loc_180063212
0x180063207  mov     [rsi+70h], r15
0x18006320b  mov     rcx, [rsp+180h+pSourceSid]
0x180063210  jmp     short loc_180063250
0x180063212  lea     rcx, [rbp+80h+pDestinationSid]; this
0x180063216  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x18006321b  nop
0x18006321c  mov     r8, [rsp+180h+pSourceSid]; pSourceSid
0x180063221  lea     rdx, [rbp+80h+pDestinationSid]; pDestinationSid
0x180063225  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18006322a  call    cs:__imp_CopySid
0x180063230  test    eax, eax
0x180063232  jnz     short loc_180063264
0x180063234  mov     [rsi+70h], r15
0x180063238  lea     rcx, [rbp+80h+var_A8]
0x18006323c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180063241  nop
0x180063242  mov     rcx, [rsp+180h+pSourceSid]; hMem
0x180063247  test    rcx, rcx
0x18006324a  jz      loc_18006332A
0x180063250  test    rcx, rcx
0x180063253  jz      loc_18006332A
0x180063259  call    cs:__imp_LocalFree
0x18006325f  jmp     loc_18006332A
0x180063264  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180063268  inc     rdx
0x18006326b  cmp     [r14+rdx*2], r15w
0x180063270  jnz     short loc_180063268
0x180063272  cmp     rdx, [rbp+80h+var_90]
0x180063276  ja      short loc_1800632A3
0x180063278  lea     rdi, [rbp+80h+var_A8]
0x18006327c  cmp     [rbp+80h+var_90], 7
0x180063281  cmova   rdi, [rbp+80h+var_A8]
0x180063286  mov     [rbp+80h+var_98], rdx
0x18006328a  lea     rbx, [rdx+rdx]
0x18006328e  mov     r8, rbx; Size
0x180063291  mov     rdx, r14; Src
0x180063294  mov     rcx, rdi; void *
0x180063297  call    memmove_0
0x18006329c  mov     [rbx+rdi], r15w
0x1800632a1  jmp     short loc_1800632AF
0x1800632a3  mov     r9, r14
0x1800632a6  lea     rcx, [rbp+80h+var_A8]
0x1800632aa  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800632af  lea     rcx, [rsi+8]
0x1800632b3  movaps  xmm0, [rbp+80h+pDestinationSid]
0x1800632b7  movups  xmmword ptr [rcx], xmm0
0x1800632ba  movaps  xmm1, [rbp+80h+var_E0]
0x1800632be  movups  xmmword ptr [rcx+10h], xmm1
0x1800632c2  movaps  xmm0, [rbp+80h+var_D0]
0x1800632c6  movups  xmmword ptr [rcx+20h], xmm0
0x1800632ca  movaps  xmm1, [rbp+80h+var_C0]
0x1800632ce  movups  xmmword ptr [rcx+30h], xmm1
0x1800632d2  mov     eax, [rbp+80h+var_B0]
0x1800632d5  mov     [rcx+40h], eax
0x1800632d8  mov     rax, [rbp+80h+var_A8]
0x1800632dc  mov     [rcx+48h], rax
0x1800632e0  mov     rax, [rbp+80h+var_A0]
0x1800632e4  mov     [rcx+50h], rax
0x1800632e8  mov     rax, [rbp+80h+var_98]
0x1800632ec  mov     [rcx+58h], rax
0x1800632f0  mov     rax, [rbp+80h+var_90]
0x1800632f4  mov     [rcx+60h], rax
0x1800632f8  mov     [rbp+80h+var_98], r15
0x1800632fc  mov     [rbp+80h+var_90], 7
0x180063304  mov     word ptr [rbp+80h+var_A8], r15w
0x180063309  mov     [rsi+70h], rcx
0x18006330d  lea     rcx, [rbp+80h+var_A8]
0x180063311  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180063316  jmp     loc_18006320B
0x18006331b  mov     ecx, 57h ; 'W'; dwErrCode
0x180063320  call    cs:__imp_SetLastError
0x180063326  mov     [rsi+70h], r15
0x18006332a  mov     rax, rsi
0x18006332d  mov     rcx, [rbp+80h+var_30]
0x180063331  xor     rcx, rsp; StackCookie
0x180063334  call    __security_check_cookie
0x180063339  mov     rbx, [rsp+180h+arg_10]
0x180063341  add     rsp, 160h
0x180063348  pop     r15
0x18006334a  pop     r14
0x18006334c  pop     rdi
0x18006334d  pop     rsi
0x18006334e  pop     rbp
0x18006334f  retn
```
