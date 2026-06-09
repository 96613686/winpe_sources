# GetAppContainerPathToProvisionFavorites(ushort const *,ushort * *)

- ea: `0x18001bc54`
- end: `0x18001bd72`
- name: `?GetAppContainerPathToProvisionFavorites@@YAJPEBGPEAPEAG@Z`
- size: `286`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180008700`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x18000dc94`
- `0x18001bc54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bcde`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18001bd29`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18001bd29`

## string_xrefs

- `0x18001bcfe`: `onecoreuap\inetcore\spartan\desktopbroker\importiefavs.cpp`

## pseudocode

```c
__int64 __fastcall GetAppContainerPathToProvisionFavorites(PCWSTR pszPathIn, unsigned __int16 **a2)
{
  PCWSTR v4; // rax
  __int64 v5; // rcx
  HRESULT v6; // ebx
  SIZE_T v7; // rbx
  void *v8; // rsi
  const char *v9; // r9
  void *v11; // [rsp+30h] [rbp-38h] BYREF
  WCHAR pszMore[8]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( pszPathIn )
  {
    v4 = pszPathIn;
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = v5 == 0 ? 0x80070057 : 0;
    if ( v5 )
    {
      wcscpy(pszMore, L"ProvFav");
      v7 = (-(__int64)(v5 != 0) & (2 * (0x7FFFFFFF - v5))) + 26;
      v8 = CoTaskMemAlloc(v7);
      CoTaskMemFree(0);
      v11 = v8;
      if ( !v8 )
        wil::details::in1diag3::_FailFast_NullAlloc(
          retaddr,
          (void *)0xF2,
          (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\importiefavs.cpp",
          v9);
      v6 = PathCchCombineEx((PWSTR)v8, v7 >> 1, pszPathIn, pszMore, 1u);
      if ( v6 >= 0 )
      {
        v11 = 0;
        *a2 = (unsigned __int16 *)v8;
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v11);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001bc54  mov     [rsp+arg_10], rbx
0x18001bc59  mov     [rsp+arg_18], rbp
0x18001bc5e  push    rsi
0x18001bc5f  push    rdi
0x18001bc60  push    r14
0x18001bc62  sub     rsp, 50h
0x18001bc66  mov     rax, cs:__security_cookie
0x18001bc6d  xor     rax, rsp
0x18001bc70  mov     [rsp+68h+var_20], rax
0x18001bc75  xor     ebp, ebp
0x18001bc77  mov     r14, rdx
0x18001bc7a  mov     rdi, rcx
0x18001bc7d  test    rcx, rcx
0x18001bc80  jz      loc_18001BD49
0x18001bc86  mov     r8d, 7FFFFFFFh
0x18001bc8c  mov     rax, rdi
0x18001bc8f  mov     ecx, r8d
0x18001bc92  cmp     [rax], bp
0x18001bc95  jz      short loc_18001BCA1
0x18001bc97  add     rax, 2
0x18001bc9b  sub     rcx, 1
0x18001bc9f  jnz     short loc_18001BC92
0x18001bca1  mov     rax, rcx
0x18001bca4  neg     rax
0x18001bca7  sbb     ebx, ebx
0x18001bca9  not     ebx
0x18001bcab  and     ebx, 80070057h
0x18001bcb1  test    rcx, rcx
0x18001bcb4  jz      loc_18001BD4E
0x18001bcba  movups  xmm0, xmmword ptr cs:aProvfav; "ProvFav"
0x18001bcc1  sub     r8, rcx
0x18001bcc4  neg     rcx
0x18001bcc7  movdqu  xmmword ptr [rsp+68h+pszMore], xmm0
0x18001bccd  sbb     rax, rax
0x18001bcd0  lea     rbx, [r8+r8]
0x18001bcd4  and     rbx, rax
0x18001bcd7  add     rbx, 1Ah
0x18001bcdb  mov     rcx, rbx; cb
0x18001bcde  call    cs:__imp_CoTaskMemAlloc
0x18001bce4  xor     ecx, ecx; pv
0x18001bce6  mov     rsi, rax
0x18001bce9  call    cs:__imp_CoTaskMemFree
0x18001bcef  mov     [rsp+68h+var_38], rsi
0x18001bcf4  test    rsi, rsi
0x18001bcf7  jnz     short loc_18001BD10
0x18001bcf9  mov     rcx, [rsp+68h]; this
0x18001bcfe  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18001bd05  mov     edx, 0F2h; void *
0x18001bd0a  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18001bd10  shr     rbx, 1
0x18001bd13  lea     r9, [rsp+68h+pszMore]; pszMore
0x18001bd18  mov     rdx, rbx; cchPathOut
0x18001bd1b  mov     [rsp+68h+dwFlags], 1; dwFlags
0x18001bd23  mov     r8, rdi; pszPathIn
0x18001bd26  mov     rcx, rsi; pszPathOut
0x18001bd29  call    cs:__imp_PathCchCombineEx
0x18001bd2f  mov     ebx, eax
0x18001bd31  test    eax, eax
0x18001bd33  js      short loc_18001BD3D
0x18001bd35  mov     [rsp+68h+var_38], rbp
0x18001bd3a  mov     [r14], rsi
0x18001bd3d  lea     rcx, [rsp+68h+var_38]
0x18001bd42  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001bd47  jmp     short loc_18001BD4E
0x18001bd49  mov     ebx, 80070057h
0x18001bd4e  mov     eax, ebx
0x18001bd50  mov     rcx, [rsp+68h+var_20]
0x18001bd55  xor     rcx, rsp; StackCookie
0x18001bd58  call    __security_check_cookie
0x18001bd5d  lea     r11, [rsp+68h+var_18]
0x18001bd62  mov     rbx, [r11+30h]
0x18001bd66  mov     rbp, [r11+38h]
0x18001bd6a  mov     rsp, r11
0x18001bd6d  pop     r14
0x18001bd6f  pop     rdi
0x18001bd70  pop     rsi
0x18001bd71  retn
```
