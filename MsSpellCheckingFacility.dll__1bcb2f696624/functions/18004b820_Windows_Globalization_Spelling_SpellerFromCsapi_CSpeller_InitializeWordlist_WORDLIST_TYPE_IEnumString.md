# Windows::Globalization::Spelling::SpellerFromCsapi::CSpeller::InitializeWordlist(WORDLIST_TYPE,IEnumString *)

- ea: `0x18004b820`
- end: `0x18004b9dd`
- name: `?InitializeWordlist@CSpeller@SpellerFromCsapi@Spelling@Globalization@Windows@@UEAAJW4WORDLIST_TYPE@@PEAUIEnumString@@@Z`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002115c`
- `0x180042f6c`
- `0x180043148`
- `0x18004b820`
- `0x18004b9e4`
- `0x18005b600`
- `0x180061320`
- `0x180062314`
- `0x1800b7bf0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b956`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::SpellerFromCsapi::CSpeller::InitializeWordlist(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  int v4; // ebx
  int Wordlist; // edi
  unsigned int v8; // eax
  _QWORD *v9; // r12
  int v10; // esi
  _QWORD *v11; // r15
  void *v12; // rbx
  int v13; // eax
  unsigned int v14; // eax
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h]
  _QWORD v19[512]; // [rsp+60h] [rbp-A0h] BYREF

  v18 = a3;
  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  if ( (unsigned int)a2 > 3 )
    return 2147942487LL;
  *(_OWORD *)v17 = 0;
  Wordlist = Windows::Globalization::Spelling::SpellerFromCsapi::CSpeller::GetWordlist(a1, a2, v17);
  if ( Wordlist >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)v17[0] + 1) + 8LL) + 120LL))(
           *(_QWORD *)(*((_QWORD *)v17[0] + 1) + 8LL),
           *((_QWORD *)v17[0] + 2));
    VerifyPtecNoErrors(v8);
    if ( v4 == 1 )
    {
      v16 = 0;
      std::unique_ptr<Windows::Globalization::Spelling::SystemUserDictionary>::~unique_ptr<Windows::Globalization::Spelling::SystemUserDictionary>(&v16);
    }
    v15 = 0;
    memset_0(v19, 0, sizeof(v19));
    Wordlist = 0;
    do
    {
      v9 = v19;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, int *))(*(_QWORD *)v3 + 24LL))(v3, 512, v19, &v15);
      if ( v19 != &v19[v15] )
      {
        v11 = &v19[v15];
        do
        {
          v12 = (void *)*v9;
          v13 = std::_Func_class<long,Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist *,unsigned short const *>::operator()(
                  a1 + 144,
                  v17[0],
                  *v9);
          if ( v13 < 0 )
            Wordlist = v13;
          v10 = 0;
          if ( v13 >= 0 )
            v10 = v13;
          CoTaskMemFree(v12);
          ++v9;
        }
        while ( v9 != v11 );
        v3 = v18;
      }
    }
    while ( !v10 );
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)v17[0] + 1) + 8LL) + 128LL))(
            *(_QWORD *)(*((_QWORD *)v17[0] + 1) + 8LL),
            *((_QWORD *)v17[0] + 2));
    VerifyPtecNoErrors(v14);
    if ( v10 != 1 )
      Wordlist = v10;
  }
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
  return (unsigned int)Wordlist;
}

```

## disassembly

```asm
0x18004b820  mov     [rsp-8+arg_18], rbx
0x18004b825  push    rbp
0x18004b826  push    rsi
0x18004b827  push    rdi
0x18004b828  push    r12
0x18004b82a  push    r13
0x18004b82c  push    r14
0x18004b82e  push    r15
0x18004b830  lea     rbp, [rsp-0F70h]
0x18004b838  mov     eax, 1070h
0x18004b83d  call    _alloca_probe
0x18004b842  sub     rsp, rax
0x18004b845  mov     rax, cs:__security_cookie
0x18004b84c  xor     rax, rsp
0x18004b84f  mov     [rbp+0FA0h+var_40], rax
0x18004b856  mov     [rsp+10A0h+var_1048], r8
0x18004b85b  mov     r15, r8
0x18004b85e  mov     ebx, edx
0x18004b860  mov     r14, rcx
0x18004b863  test    r8, r8
0x18004b866  jnz     short loc_18004B872
0x18004b868  mov     eax, 80004003h
0x18004b86d  jmp     loc_18004B9B3
0x18004b872  cmp     ebx, 3
0x18004b875  ja      loc_18004B9AE
0x18004b87b  xorps   xmm0, xmm0
0x18004b87e  lea     r8, [rsp+10A0h+var_1060]
0x18004b883  movdqu  xmmword ptr [rsp+10A0h+var_1060], xmm0
0x18004b889  call    ?GetWordlist@CSpeller@SpellerFromCsapi@Spelling@Globalization@Windows@@QEAAJW4WORDLIST_TYPE@@PEAV?$shared_ptr@VCWordlist@SpellerFromCsapi@Spelling@Globalization@Windows@@@std@@@Z; Windows::Globalization::Spelling::SpellerFromCsapi::CSpeller::GetWordlist(WORDLIST_TYPE,std::shared_ptr<Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist> *)
0x18004b88e  mov     edi, eax
0x18004b890  test    eax, eax
0x18004b892  js      loc_18004B99B
0x18004b898  mov     rdx, [rsp+10A0h+var_1060]
0x18004b89d  mov     rax, [rdx+8]
0x18004b8a1  mov     rdx, [rdx+10h]
0x18004b8a5  mov     rcx, [rax+8]
0x18004b8a9  mov     rax, [rcx]
0x18004b8ac  mov     rax, [rax+78h]
0x18004b8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8b5  mov     ecx, eax; unsigned int
0x18004b8b7  call    ?VerifyPtecNoErrors@@YAXK@Z; VerifyPtecNoErrors(ulong)
0x18004b8bc  cmp     ebx, 1
0x18004b8bf  jnz     short loc_18004B8D4
0x18004b8c1  lea     rcx, [rsp+10A0h+var_1068]
0x18004b8c6  mov     [rsp+10A0h+var_1068], 0
0x18004b8cf  call    ??1?$unique_ptr@VSystemUserDictionary@Spelling@Globalization@Windows@@U?$default_delete@VSystemUserDictionary@Spelling@Globalization@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Globalization::Spelling::SystemUserDictionary>::~unique_ptr<Windows::Globalization::Spelling::SystemUserDictionary>(void)
0x18004b8d4  xor     edx, edx; Val
0x18004b8d6  mov     [rsp+10A0h+var_1070], 0
0x18004b8de  mov     r8d, 1000h; Size
0x18004b8e4  lea     rcx, [rsp+10A0h+var_1040]; void *
0x18004b8e9  call    memset_0
0x18004b8ee  xor     edi, edi
0x18004b8f0  mov     rax, [r15]
0x18004b8f3  lea     r9, [rsp+10A0h+var_1070]
0x18004b8f8  lea     r8, [rsp+10A0h+var_1040]
0x18004b8fd  mov     edx, 200h
0x18004b902  mov     rcx, r15
0x18004b905  mov     rax, [rax+18h]
0x18004b909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b90e  mov     ecx, [rsp+10A0h+var_1070]
0x18004b912  lea     r12, [rsp+10A0h+var_1040]
0x18004b917  mov     esi, eax
0x18004b919  lea     rax, [rsp+10A0h+var_1040]
0x18004b91e  lea     rax, [rax+rcx*8]
0x18004b922  lea     rcx, [rsp+10A0h+var_1040]
0x18004b927  cmp     rcx, rax
0x18004b92a  jz      short loc_18004B96A
0x18004b92c  mov     r15, rax
0x18004b92f  mov     rbx, [r12]
0x18004b933  lea     rcx, [r14+90h]
0x18004b93a  mov     rdx, [rsp+10A0h+var_1060]
0x18004b93f  mov     r8, rbx
0x18004b942  call    ??R?$_Func_class@JPEAVCWordlist@SpellerFromCsapi@Spelling@Globalization@Windows@@PEBG@std@@QEBAJPEAVCWordlist@SpellerFromCsapi@Spelling@Globalization@Windows@@PEBG@Z; std::_Func_class<long,Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist *,ushort const *>::operator()(Windows::Globalization::Spelling::SpellerFromCsapi::CWordlist *,ushort const *)
0x18004b947  test    eax, eax
0x18004b949  mov     rcx, rbx; pv
0x18004b94c  cmovs   edi, eax
0x18004b94f  xor     esi, esi
0x18004b951  test    eax, eax
0x18004b953  cmovns  esi, eax
0x18004b956  call    cs:__imp_CoTaskMemFree
0x18004b95c  add     r12, 8
0x18004b960  cmp     r12, r15
0x18004b963  jnz     short loc_18004B92F
0x18004b965  mov     r15, [rsp+10A0h+var_1048]
0x18004b96a  test    esi, esi
0x18004b96c  jz      short loc_18004B8F0
0x18004b96e  mov     rdx, [rsp+10A0h+var_1060]
0x18004b973  mov     rax, [rdx+8]
0x18004b977  mov     rdx, [rdx+10h]
0x18004b97b  mov     rcx, [rax+8]
0x18004b97f  mov     rax, [rcx]
0x18004b982  mov     rax, [rax+80h]
0x18004b989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b98e  mov     ecx, eax; unsigned int
0x18004b990  call    ?VerifyPtecNoErrors@@YAXK@Z; VerifyPtecNoErrors(ulong)
0x18004b995  cmp     esi, 1
0x18004b998  cmovnz  edi, esi
0x18004b99b  mov     rcx, [rsp+10A0h+var_1060+8]; this
0x18004b9a0  test    rcx, rcx
0x18004b9a3  jz      short loc_18004B9AA
0x18004b9a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b9aa  mov     eax, edi
0x18004b9ac  jmp     short loc_18004B9B3
0x18004b9ae  mov     eax, 80070057h
0x18004b9b3  mov     rcx, [rbp+0FA0h+var_40]
0x18004b9ba  xor     rcx, rsp; StackCookie
0x18004b9bd  call    __security_check_cookie
0x18004b9c2  mov     rbx, [rsp+10A0h+arg_18]
0x18004b9ca  add     rsp, 1070h
0x18004b9d1  pop     r15
0x18004b9d3  pop     r14
0x18004b9d5  pop     r13
0x18004b9d7  pop     r12
0x18004b9d9  pop     rdi
0x18004b9da  pop     rsi
0x18004b9db  pop     rbp
0x18004b9dc  retn
```
