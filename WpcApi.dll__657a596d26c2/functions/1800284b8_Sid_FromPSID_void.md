# Sid::FromPSID(void *)

- ea: `0x1800284b8`
- end: `0x1800286e1`
- name: `?FromPSID@Sid@@SA?AV1@PEAX@Z`
- size: `553`
- prototype: `void **__fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800073e0`
- `0x18002883c`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180004925`
- `0x18000b29c`
- `0x180015578`
- `0x1800195c4`
- `0x180023650`
- `0x180028310`
- `0x1800284b8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002861d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002867f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002861d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002867f`
- `ADVAPI32!CopySid` at `0x180028507`
- `ADVAPI32!CopySid` at `0x180028507`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180028548`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180028548`
- `KERNEL32!LocalFree` at `0x1800285f0`
- `KERNEL32!LocalFree` at `0x1800285f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall Sid::FromPSID(void **a1, void *a2)
{
  BOOL v4; // ebx
  __int64 v5; // r8
  _BYTE *v6; // rdx
  void *v7; // r9
  void **v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  unsigned int v16; // ebx
  void *Src; // [rsp+28h] [rbp-71h] BYREF
  LPWSTR v18; // [rsp+30h] [rbp-69h] BYREF
  _QWORD pExceptionObject[9]; // [rsp+38h] [rbp-61h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v21[56]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE *v22; // [rsp+C0h] [rbp+27h]

  pExceptionObject[8] = a1;
  Sid::Sid((Sid *)a1);
  if ( !CopySid(0x44u, a1, a2) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v16);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Src = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_681c72bba3685db507962fa0cd0a806c_,void,unsigned short *>::`vftable';
  pExceptionObject[1] = &Src;
  pExceptionObject[7] = pExceptionObject;
  stdext::GetPointer<void *>::GetPointer<void *>(&StringSid, pExceptionObject);
  v4 = ConvertSidToStringSidW(a2, &StringSid);
  if ( v22 )
  {
    v18 = StringSid;
    (*(void (__fastcall **)(_BYTE *, LPWSTR *))(*(_QWORD *)v22 + 16LL))(v22, &v18);
    if ( v22 )
    {
      v6 = v21;
      LOBYTE(v6) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v6);
    }
  }
  if ( !v4 )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v14);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v14);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v7 = Src;
  v8 = a1 + 9;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)Src + v9) );
  if ( v9 > (unsigned __int64)a1[12] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, v5, Src, 1);
  }
  else
  {
    if ( (unsigned __int64)a1[12] <= 7 )
      v10 = (char *)(a1 + 9);
    else
      v10 = (char *)*v8;
    a1[11] = (void *)v9;
    v11 = 2 * v9;
    memmove_0(v10, v7, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  if ( Src )
    LocalFree(Src);
  return a1;
}

```

## disassembly

```asm
0x1800284b8  mov     [rsp-8+arg_10], rbx
0x1800284bd  mov     [rsp-8+arg_18], rsi
0x1800284c2  push    rbp
0x1800284c3  push    rdi
0x1800284c4  push    r14
0x1800284c6  lea     rbp, [rsp-47h]
0x1800284cb  sub     rsp, 0E0h
0x1800284d2  mov     rax, cs:__security_cookie
0x1800284d9  xor     rax, rsp
0x1800284dc  mov     [rbp+57h+var_20], rax
0x1800284e0  mov     rbx, rdx
0x1800284e3  mov     rsi, rcx
0x1800284e6  mov     [rbp+57h+var_78], rcx
0x1800284ea  xor     r14d, r14d
0x1800284ed  mov     [rbp+57h+var_D0], r14d
0x1800284f1  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x1800284f6  mov     [rbp+57h+var_D0], 1
0x1800284fd  mov     r8, rbx; pSourceSid
0x180028500  mov     rdx, rsi; pDestinationSid
0x180028503  lea     ecx, [r14+44h]; nDestinationSidLength
0x180028507  call    cs:__imp_CopySid
0x18002850d  test    eax, eax
0x18002850f  jz      loc_18002867F
0x180028515  mov     [rbp+57h+Src], r14
0x180028519  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_681c72bba3685db507962fa0cd0a806c_@@XPEAG@std@@6B@; const std::_Func_impl_no_alloc<_lambda_681c72bba3685db507962fa0cd0a806c_,void,ushort *>::`vftable'
0x180028520  mov     [rbp+57h+pExceptionObject], rax
0x180028524  lea     rax, [rbp+57h+Src]
0x180028528  mov     [rbp+57h+var_B0], rax
0x18002852c  lea     rax, [rbp+57h+pExceptionObject]
0x180028530  mov     [rbp+57h+var_80], rax
0x180028534  lea     rdx, [rbp+57h+pExceptionObject]
0x180028538  lea     rcx, [rbp+57h+StringSid]
0x18002853c  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x180028541  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180028545  mov     rcx, rbx; Sid
0x180028548  call    cs:__imp_ConvertSidToStringSidW
0x18002854e  mov     ebx, eax
0x180028550  mov     rcx, [rbp+57h+var_30]
0x180028554  test    rcx, rcx
0x180028557  jz      short loc_180028591
0x180028559  mov     rdx, [rbp+57h+StringSid]
0x18002855d  mov     [rbp+57h+var_C0], rdx
0x180028561  mov     rdx, [rcx]
0x180028564  mov     rax, [rdx+10h]
0x180028568  lea     rdx, [rbp+57h+var_C0]
0x18002856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028571  mov     rcx, [rbp+57h+var_30]
0x180028575  test    rcx, rcx
0x180028578  jz      short loc_180028591
0x18002857a  mov     rax, [rcx]
0x18002857d  lea     rdx, [rbp+57h+var_68]
0x180028581  cmp     rcx, rdx
0x180028584  setnz   dl
0x180028587  mov     rax, [rax+20h]
0x18002858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028590  nop
0x180028591  test    ebx, ebx
0x180028593  jz      loc_18002861D
0x180028599  mov     r9, [rbp+57h+Src]
0x18002859d  lea     rcx, [rsi+48h]
0x1800285a1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800285a5  inc     rdx
0x1800285a8  cmp     [r9+rdx*2], r14w
0x1800285ad  jnz     short loc_1800285A5
0x1800285af  cmp     rdx, [rcx+18h]
0x1800285b3  ja      short loc_1800285E1
0x1800285b5  cmp     qword ptr [rcx+18h], 7
0x1800285ba  jbe     short loc_1800285C1
0x1800285bc  mov     rdi, [rcx]
0x1800285bf  jmp     short loc_1800285C4
0x1800285c1  mov     rdi, rcx
0x1800285c4  mov     [rcx+10h], rdx
0x1800285c8  lea     rbx, [rdx+rdx]
0x1800285cc  mov     r8, rbx; Size
0x1800285cf  mov     rdx, r9; Src
0x1800285d2  mov     rcx, rdi; void *
0x1800285d5  call    memmove_0
0x1800285da  mov     [rbx+rdi], r14w
0x1800285df  jmp     short loc_1800285E7
0x1800285e1  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800285e6  nop
0x1800285e7  mov     rcx, [rbp+57h+Src]; hMem
0x1800285eb  test    rcx, rcx
0x1800285ee  jz      short loc_1800285F6
0x1800285f0  call    cs:__imp_LocalFree
0x1800285f6  mov     rax, rsi
0x1800285f9  mov     rcx, [rbp+57h+var_20]
0x1800285fd  xor     rcx, rsp; StackCookie
0x180028600  call    __security_check_cookie
0x180028605  lea     r11, [rsp+0F0h+var_10]
0x18002860d  mov     rbx, [r11+30h]
0x180028611  mov     rsi, [r11+38h]
0x180028615  mov     rsp, r11
0x180028618  pop     r14
0x18002861a  pop     rdi
0x18002861b  pop     rbp
0x18002861c  retn
0x18002861d  call    cs:__imp_GetLastError
0x180028623  mov     ebx, eax
0x180028625  test    eax, eax
0x180028627  jle     short loc_180028632
0x180028629  movzx   ebx, ax
0x18002862c  or      ebx, 80070000h
0x180028632  lea     rax, WPP_GLOBAL_Control
0x180028639  mov     rcx, cs:WPP_GLOBAL_Control
0x180028640  cmp     rcx, rax
0x180028643  jz      short loc_180028663
0x180028645  test    byte ptr [rcx+1Ch], 1
0x180028649  jz      short loc_180028663
0x18002864b  mov     edx, 0Bh
0x180028650  mov     r9d, ebx
0x180028653  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x18002865a  mov     rcx, [rcx+10h]
0x18002865e  call    WPP_SF_d
0x180028663  mov     edx, ebx; int
0x180028665  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180028669  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18002866e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180028675  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180028679  call    _CxxThrowException_0
0x18002867f  call    cs:__imp_GetLastError
0x180028685  mov     ebx, eax
0x180028687  test    eax, eax
0x180028689  jle     short loc_180028694
0x18002868b  movzx   ebx, ax
0x18002868e  or      ebx, 80070000h
0x180028694  lea     rax, WPP_GLOBAL_Control
0x18002869b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286a2  cmp     rcx, rax
0x1800286a5  jz      short loc_1800286C5
0x1800286a7  test    byte ptr [rcx+1Ch], 1
0x1800286ab  jz      short loc_1800286C5
0x1800286ad  mov     edx, 0Ah
0x1800286b2  mov     r9d, ebx
0x1800286b5  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x1800286bc  mov     rcx, [rcx+10h]
0x1800286c0  call    WPP_SF_d
0x1800286c5  mov     edx, ebx; int
0x1800286c7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800286cb  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800286d0  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800286d7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800286db  call    _CxxThrowException_0
```
