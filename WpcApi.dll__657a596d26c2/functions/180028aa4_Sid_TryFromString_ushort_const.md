# Sid::TryFromString(ushort const *)

- ea: `0x180028aa4`
- end: `0x180028cbc`
- name: `?TryFromString@Sid@@SA?AV?$Optional@VSid@@@@PEBG@Z`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800286e8`

## callees

- `0x1800032a0`
- `0x180004925`
- `0x180005f9c`
- `0x180015578`
- `0x180023650`
- `0x180028310`
- `0x180028aa4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028c8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028c8c`
- `ADVAPI32!CopySid` at `0x180028b96`
- `ADVAPI32!CopySid` at `0x180028b96`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180028b24`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180028b24`
- `KERNEL32!LocalFree` at `0x180028bc5`
- `KERNEL32!LocalFree` at `0x180028bc5`

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
      std::wstring::~wstring((char **)v17);
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
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v17,
        v8,
        v7,
        a2,
        (_DWORD)pSourceSid);
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
    std::wstring::~wstring((char **)v17);
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
0x180028aa4  mov     [rsp-8+arg_10], rbx
0x180028aa9  push    rbp
0x180028aaa  push    rsi
0x180028aab  push    rdi
0x180028aac  push    r14
0x180028aae  push    r15
0x180028ab0  lea     rbp, [rsp-60h]
0x180028ab5  sub     rsp, 160h
0x180028abc  mov     rax, cs:__security_cookie
0x180028ac3  xor     rax, rsp
0x180028ac6  mov     [rbp+80h+var_30], rax
0x180028aca  mov     r14, rdx
0x180028acd  mov     rsi, rcx
0x180028ad0  mov     [rsp+180h+var_150], rcx
0x180028ad5  xor     r15d, r15d
0x180028ad8  test    rdx, rdx
0x180028adb  jz      loc_180028C87
0x180028ae1  cmp     [rdx], r15w
0x180028ae5  jz      loc_180028C87
0x180028aeb  mov     [rsp+180h+pSourceSid], r15
0x180028af0  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1a0a9a37411416c90e606832c1826ed5_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable'
0x180028af7  mov     [rsp+180h+var_138], rax
0x180028afc  lea     rax, [rsp+180h+pSourceSid]
0x180028b01  mov     [rsp+180h+var_130], rax
0x180028b06  lea     rax, [rsp+180h+var_138]
0x180028b0b  mov     [rbp+80h+var_100], rax
0x180028b0f  lea     rdx, [rsp+180h+var_138]
0x180028b14  lea     rcx, [rbp+80h+Sid]
0x180028b18  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x180028b1d  lea     rdx, [rbp+80h+Sid]; Sid
0x180028b21  mov     rcx, r14; StringSid
0x180028b24  call    cs:__imp_ConvertStringSidToSidW
0x180028b2a  mov     ebx, eax
0x180028b2c  mov     rcx, [rbp+80h+var_40]
0x180028b30  test    rcx, rcx
0x180028b33  jz      short loc_180028B6F
0x180028b35  mov     rax, [rbp+80h+Sid]
0x180028b39  mov     [rsp+180h+var_150], rax
0x180028b3e  mov     rax, [rcx]
0x180028b41  lea     rdx, [rsp+180h+var_150]
0x180028b46  mov     rax, [rax+10h]
0x180028b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b4f  mov     rcx, [rbp+80h+var_40]
0x180028b53  test    rcx, rcx
0x180028b56  jz      short loc_180028B6F
0x180028b58  mov     rax, [rcx]
0x180028b5b  lea     rdx, [rbp+80h+var_78]
0x180028b5f  cmp     rcx, rdx
0x180028b62  setnz   dl
0x180028b65  mov     rax, [rax+20h]
0x180028b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b6e  nop
0x180028b6f  test    ebx, ebx
0x180028b71  jnz     short loc_180028B7E
0x180028b73  mov     [rsi+70h], r15
0x180028b77  mov     rcx, [rsp+180h+pSourceSid]
0x180028b7c  jmp     short loc_180028BBC
0x180028b7e  lea     rcx, [rbp+80h+pDestinationSid]; this
0x180028b82  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x180028b87  nop
0x180028b88  mov     r8, [rsp+180h+pSourceSid]; pSourceSid
0x180028b8d  lea     rdx, [rbp+80h+pDestinationSid]; pDestinationSid
0x180028b91  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180028b96  call    cs:__imp_CopySid
0x180028b9c  test    eax, eax
0x180028b9e  jnz     short loc_180028BD0
0x180028ba0  mov     [rsi+70h], r15
0x180028ba4  lea     rcx, [rbp+80h+var_A8]
0x180028ba8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028bad  nop
0x180028bae  mov     rcx, [rsp+180h+pSourceSid]; hMem
0x180028bb3  test    rcx, rcx
0x180028bb6  jz      loc_180028C96
0x180028bbc  test    rcx, rcx
0x180028bbf  jz      loc_180028C96
0x180028bc5  call    cs:__imp_LocalFree
0x180028bcb  jmp     loc_180028C96
0x180028bd0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180028bd4  inc     rdx
0x180028bd7  cmp     [r14+rdx*2], r15w
0x180028bdc  jnz     short loc_180028BD4
0x180028bde  cmp     rdx, [rbp+80h+var_90]
0x180028be2  ja      short loc_180028C0F
0x180028be4  lea     rdi, [rbp+80h+var_A8]
0x180028be8  cmp     [rbp+80h+var_90], 7
0x180028bed  cmova   rdi, [rbp+80h+var_A8]
0x180028bf2  mov     [rbp+80h+var_98], rdx
0x180028bf6  lea     rbx, [rdx+rdx]
0x180028bfa  mov     r8, rbx; Size
0x180028bfd  mov     rdx, r14; Src
0x180028c00  mov     rcx, rdi; void *
0x180028c03  call    memmove_0
0x180028c08  mov     [rbx+rdi], r15w
0x180028c0d  jmp     short loc_180028C1B
0x180028c0f  mov     r9, r14
0x180028c12  lea     rcx, [rbp+80h+var_A8]
0x180028c16  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180028c1b  lea     rcx, [rsi+8]
0x180028c1f  movaps  xmm0, [rbp+80h+pDestinationSid]
0x180028c23  movups  xmmword ptr [rcx], xmm0
0x180028c26  movaps  xmm1, [rbp+80h+var_E0]
0x180028c2a  movups  xmmword ptr [rcx+10h], xmm1
0x180028c2e  movaps  xmm0, [rbp+80h+var_D0]
0x180028c32  movups  xmmword ptr [rcx+20h], xmm0
0x180028c36  movaps  xmm1, [rbp+80h+var_C0]
0x180028c3a  movups  xmmword ptr [rcx+30h], xmm1
0x180028c3e  mov     eax, [rbp+80h+var_B0]
0x180028c41  mov     [rcx+40h], eax
0x180028c44  mov     rax, [rbp+80h+var_A8]
0x180028c48  mov     [rcx+48h], rax
0x180028c4c  mov     rax, [rbp+80h+var_A0]
0x180028c50  mov     [rcx+50h], rax
0x180028c54  mov     rax, [rbp+80h+var_98]
0x180028c58  mov     [rcx+58h], rax
0x180028c5c  mov     rax, [rbp+80h+var_90]
0x180028c60  mov     [rcx+60h], rax
0x180028c64  mov     [rbp+80h+var_98], r15
0x180028c68  mov     [rbp+80h+var_90], 7
0x180028c70  mov     word ptr [rbp+80h+var_A8], r15w
0x180028c75  mov     [rsi+70h], rcx
0x180028c79  lea     rcx, [rbp+80h+var_A8]
0x180028c7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c82  jmp     loc_180028B77
0x180028c87  mov     ecx, 57h ; 'W'; dwErrCode
0x180028c8c  call    cs:__imp_SetLastError
0x180028c92  mov     [rsi+70h], r15
0x180028c96  mov     rax, rsi
0x180028c99  mov     rcx, [rbp+80h+var_30]
0x180028c9d  xor     rcx, rsp; StackCookie
0x180028ca0  call    __security_check_cookie
0x180028ca5  mov     rbx, [rsp+180h+arg_10]
0x180028cad  add     rsp, 160h
0x180028cb4  pop     r15
0x180028cb6  pop     r14
0x180028cb8  pop     rdi
0x180028cb9  pop     rsi
0x180028cba  pop     rbp
0x180028cbb  retn
```
