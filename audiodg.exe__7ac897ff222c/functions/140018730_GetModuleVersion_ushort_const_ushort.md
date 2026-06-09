# GetModuleVersion(ushort const *,ushort * *)

- ea: `0x140018730`
- end: `0x140018902`
- name: `?GetModuleVersion@@YAXPEBGPEAPEAG@Z`
- size: `466`
- prototype: `void __fastcall(LPCWSTR lptstrFilename, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140054f5c`
- `0x140081a60`

## callees

- `0x140016f68`
- `0x140018730`
- `0x140018e68`
- `0x14005d0e0`
- `0x14005d4ac`
- `0x14005d7c8`
- `0x14005e07e`
- `0x14005e150`
- `0x14005e168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188ec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400188ec`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1400187b2`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1400187b2`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x140018770`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x140018770`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1400187d6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1400187d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400188a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400188a2`

## pseudocode

```c
void __fastcall GetModuleVersion(LPCWSTR lptstrFilename, unsigned __int16 **a2)
{
  DWORD FileVersionInfoSizeW; // eax
  DWORD v5; // edi
  void *v6; // rax
  void *v7; // rsi
  unsigned __int16 *v8; // rbx
  size_t v9; // rdi
  size_t v10; // r14
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  unsigned int puLen; // [rsp+40h] [rbp-79h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int16 *v16; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 Src[64]; // [rsp+60h] [rbp-59h] BYREF

  if ( lptstrFilename )
  {
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, 0);
    v5 = FileVersionInfoSizeW;
    if ( FileVersionInfoSizeW )
    {
      v6 = operator new[](FileVersionInfoSizeW, (const struct std::nothrow_t *)std::nothrow);
      v7 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, v5);
        if ( GetFileVersionInfoW(lptstrFilename, 0, v5, v7) )
        {
          lpBuffer = 0;
          puLen = 0;
          if ( VerQueryValueW(v7, L"\\", &lpBuffer, &puLen) )
          {
            if ( puLen )
            {
              memset_0(Src, 0, sizeof(Src));
              if ( (int)StringCchPrintfW(
                          Src,
                          0x40u,
                          L"%d.%d.%d.%d",
                          *((unsigned __int16 *)lpBuffer + 5),
                          *((unsigned __int16 *)lpBuffer + 4),
                          *((unsigned __int16 *)lpBuffer + 7),
                          *((unsigned __int16 *)lpBuffer + 6)) >= 0 )
              {
                v13 = 0x7FFFFFFF;
                v12 = Src;
                do
                {
                  if ( !*v12 )
                    break;
                  ++v12;
                  --v13;
                }
                while ( v13 );
                v9 = 2 * (v12 - Src);
                v10 = v9 + 2;
                v11 = (unsigned __int16 *)CoTaskMemAlloc(v9 + 2);
                v8 = v11;
                if ( v11 )
                {
                  if ( v9 )
                  {
                    if ( v10 < v9 )
                    {
                      memset_0(v11, 0, v10);
                      *(_DWORD *)_o__errno() = 34;
                      invalid_parameter_noinfo();
                    }
                    else
                    {
                      memcpy_0(v11, Src, v9);
                    }
                  }
                  v8[v9 / 2] = 0;
                  *a2 = v8;
                  v8 = 0;
                }
                v16 = v8;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v16);
              }
            }
          }
        }
        operator delete(v7);
      }
    }
  }
}

```

## disassembly

```asm
0x140018730  test    rcx, rcx
0x140018733  jz      locret_14001886C
0x140018739  mov     [rsp-8+arg_10], rbx
0x14001873e  mov     [rsp-8+arg_18], rsi
0x140018743  push    rbp
0x140018744  push    rdi
0x140018745  push    r12
0x140018747  push    r14
0x140018749  push    r15
0x14001874b  lea     rbp, [rsp-37h]
0x140018750  sub     rsp, 0F0h
0x140018757  mov     rax, cs:__security_cookie
0x14001875e  xor     rax, rsp
0x140018761  mov     [rbp+57h+var_30], rax
0x140018765  mov     r15, rdx
0x140018768  mov     rbx, rcx
0x14001876b  xor     edx, edx; lpdwHandle
0x14001876d  xor     r12d, r12d
0x140018770  call    cs:__imp_GetFileVersionInfoSizeW
0x140018776  mov     edi, eax
0x140018778  test    eax, eax
0x14001877a  jz      loc_140018845
0x140018780  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018787  mov     ecx, edi; unsigned __int64
0x140018789  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001878e  mov     rsi, rax
0x140018791  test    rax, rax
0x140018794  jz      loc_140018845
0x14001879a  mov     r8d, edi; Size
0x14001879d  xor     edx, edx; Val
0x14001879f  mov     rcx, rax; void *
0x1400187a2  call    memset_0
0x1400187a7  mov     r9, rsi; lpData
0x1400187aa  mov     r8d, edi; dwLen
0x1400187ad  xor     edx, edx; dwHandle
0x1400187af  mov     rcx, rbx; lptstrFilename
0x1400187b2  call    cs:__imp_GetFileVersionInfoW
0x1400187b8  test    eax, eax
0x1400187ba  jz      short loc_140018838
0x1400187bc  lea     r9, [rbp+57h+puLen]; puLen
0x1400187c0  mov     [rbp+57h+lpBuffer], r12
0x1400187c4  lea     r8, [rbp+57h+lpBuffer]; lplpBuffer
0x1400187c8  mov     [rbp+57h+puLen], r12d
0x1400187cc  lea     rdx, SubBlock; "\\"
0x1400187d3  mov     rcx, rsi; pBlock
0x1400187d6  call    cs:__imp_VerQueryValueW
0x1400187dc  test    eax, eax
0x1400187de  jz      short loc_140018838
0x1400187e0  cmp     [rbp+57h+puLen], r12d
0x1400187e4  jbe     short loc_140018838
0x1400187e6  xor     edx, edx; Val
0x1400187e8  lea     rcx, [rbp+57h+Src]; void *
0x1400187ec  mov     r8d, 80h; Size
0x1400187f2  call    memset_0
0x1400187f7  mov     r8, [rbp+57h+lpBuffer]
0x1400187fb  movzx   ecx, word ptr [r8+0Eh]
0x140018800  movzx   edx, word ptr [r8+8]
0x140018805  movzx   eax, word ptr [r8+0Ch]
0x14001880a  movzx   r9d, word ptr [r8+0Ah]
0x14001880f  lea     r8, aDDDD; "%d.%d.%d.%d"
0x140018816  mov     [rsp+110h+var_E0], eax
0x14001881a  mov     [rsp+110h+var_E8], ecx
0x14001881e  lea     rcx, [rbp+57h+Src]; unsigned __int16 *
0x140018822  mov     [rsp+110h+var_F0], edx
0x140018826  lea     edx, [r12+40h]; unsigned __int64
0x14001882b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018830  test    eax, eax
0x140018832  jns     loc_1400188D7
0x140018838  mov     edx, 1
0x14001883d  mov     rcx, rsi; Block
0x140018840  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140018845  mov     rcx, [rbp+57h+var_30]
0x140018849  xor     rcx, rsp; StackCookie
0x14001884c  call    __security_check_cookie
0x140018851  lea     r11, [rsp+110h+var_20]
0x140018859  mov     rbx, [r11+40h]
0x14001885d  mov     rsi, [r11+48h]
0x140018861  mov     rsp, r11
0x140018864  pop     r15
0x140018866  pop     r14
0x140018868  pop     r12
0x14001886a  pop     rdi
0x14001886b  pop     rbp
0x14001886c  retn
0x14001886d  mov     [rdi+rbx], r12w
0x140018872  mov     [r15], rbx
0x140018875  mov     rbx, r12
0x140018878  lea     rcx, [rbp+57h+var_C0]
0x14001887c  mov     [rbp+57h+var_C0], rbx
0x140018880  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140018885  jmp     short loc_140018838
0x140018887  cmp     [rax], r12w
0x14001888b  jnz     short loc_1400188CB
0x14001888d  lea     rcx, [rbp+57h+Src]
0x140018891  sub     rax, rcx
0x140018894  sar     rax, 1
0x140018897  lea     rdi, [rax+rax]
0x14001889b  lea     r14, [rdi+2]
0x14001889f  mov     rcx, r14; cb
0x1400188a2  call    cs:__imp_CoTaskMemAlloc
0x1400188a8  mov     rbx, rax
0x1400188ab  test    rax, rax
0x1400188ae  jz      short loc_140018878
0x1400188b0  test    rdi, rdi
0x1400188b3  jz      short loc_14001886D
0x1400188b5  mov     rcx, rax; void *
0x1400188b8  cmp     r14, rdi
0x1400188bb  jb      short loc_1400188E2
0x1400188bd  mov     r8, rdi; Size
0x1400188c0  lea     rdx, [rbp+57h+Src]; Src
0x1400188c4  call    memcpy_0
0x1400188c9  jmp     short loc_14001886D
0x1400188cb  add     rax, 2
0x1400188cf  sub     rcx, 1
0x1400188d3  jnz     short loc_140018887
0x1400188d5  jmp     short loc_14001888D
0x1400188d7  mov     ecx, 7FFFFFFFh
0x1400188dc  lea     rax, [rbp+57h+Src]
0x1400188e0  jmp     short loc_140018887
0x1400188e2  mov     r8, r14; Size
0x1400188e5  xor     edx, edx; Val
0x1400188e7  call    memset_0
0x1400188ec  call    cs:__imp__o__errno
0x1400188f2  mov     dword ptr [rax], 22h ; '"'
0x1400188f8  call    _invalid_parameter_noinfo
0x1400188fd  jmp     loc_14001886D
```
