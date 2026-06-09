# MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)

- ea: `0x18000a9c0`
- end: `0x18000ab92`
- name: `?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct tagPROPVARIANT *)`
- caller_count: `6`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008640`
- `0x18000a504`
- `0x18000a5d0`
- `0x180012fd8`
- `0x18001a6a8`
- `0x18001a8ec`

## callees

- `0x18000a9c0`
- `0x1800112a4`
- `0x18001b98a`
- `0x18001ba48`
- `0x18003eda8`
- `0x18003edbc`
- `0x18003ee20`
- `0x18003f2b4`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aad9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aaa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aa20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aaa7`

## pseudocode

```c
__int64 __fastcall MultiSzToPropVariant(const unsigned __int16 *Src, struct tagPROPVARIANT *a2)
{
  __int64 v2; // r15
  const unsigned __int16 *v4; // rbx
  const unsigned __int16 *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax
  bool v8; // zf
  void *v9; // rax
  void *v10; // rdi
  __int64 result; // rax
  unsigned int v12; // r12d
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  size_t v15; // rdi
  size_t v16; // rbp
  char *v17; // rax
  char *v18; // rsi
  _QWORD *v19; // rax
  __int64 v20; // rax
  int v21[18]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  LODWORD(v2) = 0;
  v4 = Src;
  v5 = Src;
  if ( *Src )
  {
    do
    {
      v2 = (unsigned int)(v2 + 1);
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      v7 = (unsigned int)(v6 + 1);
      v8 = v5[v7] == 0;
      v5 += v7;
    }
    while ( !v8 );
    if ( (_DWORD)v2 )
    {
      v9 = CoTaskMemAlloc(8LL * (unsigned int)v2);
      v10 = v9;
      if ( !v9 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
          (const char *)0x8007000ELL,
          v21[0]);
        return 2147942414LL;
      }
      memset_0(v9, 0, 8 * v2);
      wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(
        v21,
        v10,
        (unsigned int)v2);
      v12 = 0;
      while ( *v4 )
      {
        v13 = 0x7FFFFFFF;
        v14 = v4;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v13;
        }
        while ( v13 );
        v15 = 2 * (v14 - v4);
        v16 = v15 + 2;
        v17 = (char *)CoTaskMemAlloc(v15 + 2);
        v18 = v17;
        if ( !v17 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x360,
            (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
            (const char *)0x8007000ELL,
            v21[0]);
          wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>((__int64)v21);
          return 2147942414LL;
        }
        if ( v15 )
        {
          if ( v16 < v15 )
          {
            memset_0(v17, 0, v16);
            *(_DWORD *)_o__errno() = 34;
            invalid_parameter_noinfo();
          }
          else
          {
            memcpy_0(v17, v4, v15);
          }
        }
        *(_WORD *)&v18[v15] = 0;
        v19 = (_QWORD *)wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::operator[](
                          v21,
                          v12++);
        *v19 = v18;
        v20 = -1;
        do
          ++v20;
        while ( v4[v20] );
        v4 += (unsigned int)(v20 + 1);
      }
      a2->bstrblobVal.pData = (BYTE *)wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::release(v21);
      wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>((__int64)v21);
    }
  }
  a2->vt = 4127;
  result = 0;
  a2->lVal = v2;
  return result;
}

```

## disassembly

```asm
0x18000a9c0  push    rbx
0x18000a9c2  push    rbp
0x18000a9c3  push    rsi
0x18000a9c4  push    rdi
0x18000a9c5  push    r12
0x18000a9c7  push    r14
0x18000a9c9  push    r15
0x18000a9cb  sub     rsp, 30h
0x18000a9cf  xor     r15d, r15d
0x18000a9d2  mov     r14, rdx
0x18000a9d5  mov     rbx, rcx
0x18000a9d8  mov     r8, rcx
0x18000a9db  cmp     [rcx], r15w
0x18000a9df  jz      loc_18000AB77
0x18000a9e5  inc     r15d
0x18000a9e8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a9ef  nop
0x18000a9f0  inc     rax
0x18000a9f3  cmp     word ptr [r8+rax*2], 0
0x18000a9f9  jnz     short loc_18000A9F0
0x18000a9fb  inc     eax
0x18000a9fd  cmp     word ptr [r8+rax*2], 0
0x18000aa03  lea     r8, [r8+rax*2]
0x18000aa07  jnz     short loc_18000A9E5
0x18000aa09  test    r15d, r15d
0x18000aa0c  jz      loc_18000AB77
0x18000aa12  lea     rbp, ds:0[r15*8]
0x18000aa1a  mov     esi, r15d
0x18000aa1d  mov     rcx, rbp; cb
0x18000aa20  call    cs:__imp_CoTaskMemAlloc
0x18000aa26  mov     rdi, rax
0x18000aa29  test    rax, rax
0x18000aa2c  jnz     short loc_18000AA54
0x18000aa2e  mov     rcx, [rsp+68h]; this
0x18000aa33  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000aa3a  mov     r9d, 8007000Eh; char *
0x18000aa40  mov     edx, 354h; void *
0x18000aa45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa4a  mov     eax, 8007000Eh
0x18000aa4f  jmp     loc_18000AB83
0x18000aa54  mov     r8, rbp; Size
0x18000aa57  xor     edx, edx; Val
0x18000aa59  mov     rcx, rdi; void *
0x18000aa5c  call    memset_0
0x18000aa61  mov     r8, rsi
0x18000aa64  lea     rcx, [rsp+68h+var_48]
0x18000aa69  mov     rdx, rdi
0x18000aa6c  call    ??0?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAA@PEAPEAG_K@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(ushort * *,unsigned __int64)
0x18000aa71  xor     r12d, r12d
0x18000aa74  cmp     word ptr [rbx], 0
0x18000aa78  jz      loc_18000AB5F
0x18000aa7e  mov     ecx, 7FFFFFFFh
0x18000aa83  mov     rax, rbx
0x18000aa86  cmp     word ptr [rax], 0
0x18000aa8a  jz      short loc_18000AA96
0x18000aa8c  add     rax, 2
0x18000aa90  sub     rcx, 1
0x18000aa94  jnz     short loc_18000AA86
0x18000aa96  sub     rax, rbx
0x18000aa99  sar     rax, 1
0x18000aa9c  lea     rdi, [rax+rax]
0x18000aaa0  lea     rbp, [rdi+2]
0x18000aaa4  mov     rcx, rbp; cb
0x18000aaa7  call    cs:__imp_CoTaskMemAlloc
0x18000aaad  mov     rsi, rax
0x18000aab0  test    rax, rax
0x18000aab3  jz      short loc_18000AB25
0x18000aab5  test    rdi, rdi
0x18000aab8  jz      short loc_18000AAEA
0x18000aaba  mov     rcx, rax; void *
0x18000aabd  cmp     rbp, rdi
0x18000aac0  jb      short loc_18000AACF
0x18000aac2  mov     r8, rdi; Size
0x18000aac5  mov     rdx, rbx; Src
0x18000aac8  call    memcpy_0
0x18000aacd  jmp     short loc_18000AAEA
0x18000aacf  mov     r8, rbp; Size
0x18000aad2  xor     edx, edx; Val
0x18000aad4  call    memset_0
0x18000aad9  call    cs:__imp__o__errno
0x18000aadf  mov     dword ptr [rax], 22h ; '"'
0x18000aae5  call    _invalid_parameter_noinfo
0x18000aaea  xor     eax, eax
0x18000aaec  mov     edx, r12d
0x18000aaef  lea     rcx, [rsp+68h+var_48]
0x18000aaf4  mov     [rdi+rsi], ax
0x18000aaf8  call    ??A?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAAAEAPEAG_K@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::operator[](unsigned __int64)
0x18000aafd  inc     r12d
0x18000ab00  mov     [rax], rsi
0x18000ab03  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ab0a  nop     word ptr [rax+rax+00h]
0x18000ab10  inc     rax
0x18000ab13  cmp     word ptr [rbx+rax*2], 0
0x18000ab18  jnz     short loc_18000AB10
0x18000ab1a  inc     eax
0x18000ab1c  lea     rbx, [rbx+rax*2]
0x18000ab20  jmp     loc_18000AA74
0x18000ab25  mov     rcx, [rsp+68h]; this
0x18000ab2a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000ab31  mov     r9d, 8007000Eh; char *
0x18000ab37  mov     edx, 360h; void *
0x18000ab3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab41  lea     rcx, [rsp+68h+var_48]
0x18000ab46  call    ??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x18000ab4b  mov     eax, 8007000Eh
0x18000ab50  add     rsp, 30h
0x18000ab54  pop     r15
0x18000ab56  pop     r14
0x18000ab58  pop     r12
0x18000ab5a  pop     rdi
0x18000ab5b  pop     rsi
0x18000ab5c  pop     rbp
0x18000ab5d  pop     rbx
0x18000ab5e  retn
0x18000ab5f  lea     rcx, [rsp+68h+var_48]
0x18000ab64  call    ?release@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAAPEAPEAGXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::release(void)
0x18000ab69  lea     rcx, [rsp+68h+var_48]
0x18000ab6e  mov     [r14+10h], rax
0x18000ab72  call    ??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x18000ab77  mov     word ptr [r14], 101Fh
0x18000ab7d  xor     eax, eax
0x18000ab7f  mov     [r14+8], r15d
0x18000ab83  add     rsp, 30h
0x18000ab87  pop     r15
0x18000ab89  pop     r14
0x18000ab8b  pop     r12
0x18000ab8d  pop     rdi
0x18000ab8e  pop     rsi
0x18000ab8f  pop     rbp
0x18000ab90  pop     rbx
0x18000ab91  retn
```
