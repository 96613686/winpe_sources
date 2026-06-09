# Sid::FromPSID(void *)

- ea: `0x1800625fc`
- end: `0x18006282b`
- name: `?FromPSID@Sid@@SA?AV1@PEAX@Z`
- size: `559`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062250`
- `0x180062ac8`
- `0x180062d28`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180007ed9`
- `0x18000ecc0`
- `0x1800157f8`
- `0x18001f348`
- `0x180035e0c`
- `0x180062344`
- `0x1800625fc`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800627c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800627c9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006264d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006264d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006273a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006273a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180062690`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180062690`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  void *Src; // [rsp+28h] [rbp-81h] BYREF
  LPWSTR v18; // [rsp+30h] [rbp-79h] BYREF
  _QWORD pExceptionObject[11]; // [rsp+38h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v21[56]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE *v22; // [rsp+D0h] [rbp+27h]

  pExceptionObject[9] = a1;
  Sid::Sid((Sid *)a1);
  if ( !CopySid(0x44u, a1, a2) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v16);
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v14);
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
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, v5, Src);
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
0x1800625fc  mov     [rsp-8+arg_10], rbx
0x180062601  mov     [rsp-8+arg_18], rsi
0x180062606  push    rbp
0x180062607  push    rdi
0x180062608  push    r14
0x18006260a  lea     rbp, [rsp-47h]
0x18006260f  sub     rsp, 0F0h
0x180062616  mov     rax, cs:__security_cookie
0x18006261d  xor     rax, rsp
0x180062620  mov     [rbp+57h+var_20], rax
0x180062624  mov     rbx, rdx
0x180062627  mov     rsi, rcx
0x18006262a  mov     [rbp+57h+var_80], rcx
0x18006262e  xor     r14d, r14d
0x180062631  mov     [rsp+100h+var_E0], r14d
0x180062636  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x18006263b  mov     [rsp+100h+var_E0], 1
0x180062643  mov     r8, rbx; pSourceSid
0x180062646  mov     rdx, rsi; pDestinationSid
0x180062649  lea     ecx, [r14+44h]; nDestinationSidLength
0x18006264d  call    cs:__imp_CopySid
0x180062653  test    eax, eax
0x180062655  jz      loc_1800627C9
0x18006265b  mov     [rsp+100h+Src], r14
0x180062660  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_681c72bba3685db507962fa0cd0a806c_@@XPEAG@std@@6B@; const std::_Func_impl_no_alloc<_lambda_681c72bba3685db507962fa0cd0a806c_,void,ushort *>::`vftable'
0x180062667  mov     [rbp+57h+pExceptionObject], rax
0x18006266b  lea     rax, [rsp+100h+Src]
0x180062670  mov     [rbp+57h+var_C0], rax
0x180062674  lea     rax, [rbp+57h+pExceptionObject]
0x180062678  mov     [rbp+57h+var_90], rax
0x18006267c  lea     rdx, [rbp+57h+pExceptionObject]
0x180062680  lea     rcx, [rbp+57h+StringSid]
0x180062684  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x180062689  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18006268d  mov     rcx, rbx; Sid
0x180062690  call    cs:__imp_ConvertSidToStringSidW
0x180062696  mov     ebx, eax
0x180062698  mov     rcx, [rbp+57h+var_30]
0x18006269c  test    rcx, rcx
0x18006269f  jz      short loc_1800626D9
0x1800626a1  mov     rdx, [rbp+57h+StringSid]
0x1800626a5  mov     [rbp+57h+var_D0], rdx
0x1800626a9  mov     rdx, [rcx]
0x1800626ac  mov     rax, [rdx+10h]
0x1800626b0  lea     rdx, [rbp+57h+var_D0]
0x1800626b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626b9  mov     rcx, [rbp+57h+var_30]
0x1800626bd  test    rcx, rcx
0x1800626c0  jz      short loc_1800626D9
0x1800626c2  mov     rax, [rcx]
0x1800626c5  lea     rdx, [rbp+57h+var_68]
0x1800626c9  cmp     rcx, rdx
0x1800626cc  setnz   dl
0x1800626cf  mov     rax, [rax+20h]
0x1800626d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626d8  nop
0x1800626d9  test    ebx, ebx
0x1800626db  jz      loc_180062767
0x1800626e1  mov     r9, [rsp+100h+Src]
0x1800626e6  lea     rcx, [rsi+48h]
0x1800626ea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800626ee  inc     rdx
0x1800626f1  cmp     [r9+rdx*2], r14w
0x1800626f6  jnz     short loc_1800626EE
0x1800626f8  cmp     rdx, [rcx+18h]
0x1800626fc  ja      short loc_18006272A
0x1800626fe  cmp     qword ptr [rcx+18h], 7
0x180062703  jbe     short loc_18006270A
0x180062705  mov     rdi, [rcx]
0x180062708  jmp     short loc_18006270D
0x18006270a  mov     rdi, rcx
0x18006270d  mov     [rcx+10h], rdx
0x180062711  lea     rbx, [rdx+rdx]
0x180062715  mov     r8, rbx; Size
0x180062718  mov     rdx, r9; Src
0x18006271b  mov     rcx, rdi; void *
0x18006271e  call    memmove_0
0x180062723  mov     [rbx+rdi], r14w
0x180062728  jmp     short loc_180062730
0x18006272a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18006272f  nop
0x180062730  mov     rcx, [rsp+100h+Src]; hMem
0x180062735  test    rcx, rcx
0x180062738  jz      short loc_180062740
0x18006273a  call    cs:__imp_LocalFree
0x180062740  mov     rax, rsi
0x180062743  mov     rcx, [rbp+57h+var_20]
0x180062747  xor     rcx, rsp; StackCookie
0x18006274a  call    __security_check_cookie
0x18006274f  lea     r11, [rsp+100h+var_10]
0x180062757  mov     rbx, [r11+30h]
0x18006275b  mov     rsi, [r11+38h]
0x18006275f  mov     rsp, r11
0x180062762  pop     r14
0x180062764  pop     rdi
0x180062765  pop     rbp
0x180062766  retn
0x180062767  call    cs:__imp_GetLastError
0x18006276d  mov     ebx, eax
0x18006276f  test    eax, eax
0x180062771  jle     short loc_18006277C
0x180062773  movzx   ebx, ax
0x180062776  or      ebx, 80070000h
0x18006277c  lea     rax, WPP_GLOBAL_Control
0x180062783  mov     rcx, cs:WPP_GLOBAL_Control
0x18006278a  cmp     rcx, rax
0x18006278d  jz      short loc_1800627AD
0x18006278f  test    byte ptr [rcx+1Ch], 1
0x180062793  jz      short loc_1800627AD
0x180062795  mov     edx, 0Bh
0x18006279a  mov     r9d, ebx
0x18006279d  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x1800627a4  mov     rcx, [rcx+10h]
0x1800627a8  call    WPP_SF_d
0x1800627ad  mov     edx, ebx; int
0x1800627af  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800627b3  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800627b8  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800627bf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800627c3  call    _CxxThrowException_0
0x1800627c9  call    cs:__imp_GetLastError
0x1800627cf  mov     ebx, eax
0x1800627d1  test    eax, eax
0x1800627d3  jle     short loc_1800627DE
0x1800627d5  movzx   ebx, ax
0x1800627d8  or      ebx, 80070000h
0x1800627de  lea     rax, WPP_GLOBAL_Control
0x1800627e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627ec  cmp     rcx, rax
0x1800627ef  jz      short loc_18006280F
0x1800627f1  test    byte ptr [rcx+1Ch], 1
0x1800627f5  jz      short loc_18006280F
0x1800627f7  mov     edx, 0Ah
0x1800627fc  mov     r9d, ebx
0x1800627ff  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180062806  mov     rcx, [rcx+10h]
0x18006280a  call    WPP_SF_d
0x18006280f  mov     edx, ebx; int
0x180062811  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180062815  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18006281a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180062821  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180062825  call    _CxxThrowException_0
```
