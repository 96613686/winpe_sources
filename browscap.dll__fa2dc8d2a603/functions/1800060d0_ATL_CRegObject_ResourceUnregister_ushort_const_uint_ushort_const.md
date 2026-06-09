# ATL::CRegObject::ResourceUnregister(ushort const *,uint,ushort const *)

- ea: `0x1800060d0`
- end: `0x1800061e6`
- name: `?ResourceUnregister@CRegObject@ATL@@QEAAJPEBGI0@Z`
- size: `278`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000672c`

## callees

- `0x1800050c0`
- `0x1800060d0`
- `0x180007034`
- `0x18000b640`

## import_xrefs

- `msvcrt!free` at `0x1800061a6`
- `msvcrt!free` at `0x1800061bd`
- `msvcrt!free` at `0x1800061a6`
- `msvcrt!free` at `0x1800061bd`
- `msvcrt!malloc` at `0x180006120`
- `msvcrt!malloc` at `0x180006120`
- `KERNEL32!WideCharToMultiByte` at `0x180006178`
- `KERNEL32!WideCharToMultiByte` at `0x180006178`

## string_xrefs

- `0x18000616c`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ResourceUnregister(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v9; // rax
  unsigned int v10; // edi
  void *v11; // rcx
  void *v13; // rcx
  CHAR MultiByteStr[8]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD *v15; // [rsp+40h] [rbp+0h]

  v7 = 0;
  v15 = 0;
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x12, (unsigned __int64)a2) )
  {
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    v9 = malloc(0x22u);
    if ( v9 )
    {
      *v9 = 0;
      v7 = v9;
      v15 = v9;
      lpMultiByteStr = (CHAR *)(v9 + 2);
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( lpMultiByteStr && (*lpMultiByteStr = 0, WideCharToMultiByte(3u, 0, L"REGISTRY", -1, lpMultiByteStr, 18, 0, 0)) )
  {
    v10 = ATL::CRegObject::RegisterFromResource(this, a2, (const char *)a3, lpMultiByteStr, 0);
    while ( v7 )
    {
      v11 = v7;
      v7 = (_QWORD *)*v7;
      free(v11);
    }
    return v10;
  }
  else
  {
    while ( v7 )
    {
      v13 = v7;
      v7 = (_QWORD *)*v7;
      free(v13);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800060d0  push    rbp
0x1800060d2  push    rbx
0x1800060d3  push    rsi
0x1800060d4  push    rdi
0x1800060d5  push    r14
0x1800060d7  push    r15
0x1800060d9  sub     rsp, 58h
0x1800060dd  lea     rbp, [rsp+40h]
0x1800060e2  mov     rax, cs:__security_cookie
0x1800060e9  xor     rax, rbp
0x1800060ec  mov     [rbp+40h+var_38], rax
0x1800060f0  mov     esi, r8d
0x1800060f3  mov     r14, rdx
0x1800060f6  mov     r15, rcx
0x1800060f9  xor     ebx, ebx
0x1800060fb  mov     [rbp+40h+var_40], rbx
0x1800060ff  lea     ecx, [rbx+12h]; this
0x180006102  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180006107  test    al, al
0x180006109  jz      short loc_18000611B
0x18000610b  mov     eax, dword ptr [rsp+80h+lpMultiByteStr]
0x18000610e  sub     rsp, 20h
0x180006112  lea     rdi, [rsp+0A0h+MultiByteStr]
0x180006117  mov     eax, [rdi]
0x180006119  jmp     short loc_180006141
0x18000611b  mov     ecx, 22h ; '"'; Size
0x180006120  call    cs:__imp_malloc
0x180006126  test    rax, rax
0x180006129  jnz     short loc_18000612F
0x18000612b  xor     edi, edi
0x18000612d  jmp     short loc_180006141
0x18000612f  mov     qword ptr [rax], 0
0x180006136  mov     rbx, rax
0x180006139  mov     [rbp+40h+var_40], rax
0x18000613d  lea     rdi, [rax+10h]
0x180006141  test    rdi, rdi
0x180006144  jz      short loc_1800061B5
0x180006146  mov     byte ptr [rdi], 0
0x180006149  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180006152  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x18000615b  mov     [rsp+0A0h+cbMultiByte], 12h; cbMultiByte
0x180006163  mov     [rsp+0A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180006168  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000616c  lea     r8, WideCharStr; "REGISTRY"
0x180006173  xor     edx, edx; dwFlags
0x180006175  lea     ecx, [rdx+3]; CodePage
0x180006178  call    cs:__imp_WideCharToMultiByte
0x18000617e  test    eax, eax
0x180006180  jz      short loc_1800061B5
0x180006182  movzx   r8d, si; char *
0x180006186  mov     dword ptr [rsp+0A0h+lpMultiByteStr], 0; int
0x18000618e  mov     r9, rdi; char *
0x180006191  mov     rdx, r14; unsigned __int16 *
0x180006194  mov     rcx, r15; this
0x180006197  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x18000619c  mov     edi, eax
0x18000619e  jmp     short loc_1800061AC
0x1800061a0  mov     rcx, rbx; Block
0x1800061a3  mov     rbx, [rbx]
0x1800061a6  call    cs:__imp_free
0x1800061ac  test    rbx, rbx
0x1800061af  jnz     short loc_1800061A0
0x1800061b1  mov     eax, edi
0x1800061b3  jmp     short loc_1800061CD
0x1800061b5  jmp     short loc_1800061C3
0x1800061b7  mov     rcx, rbx; Block
0x1800061ba  mov     rbx, [rbx]
0x1800061bd  call    cs:__imp_free
0x1800061c3  test    rbx, rbx
0x1800061c6  jnz     short loc_1800061B7
0x1800061c8  mov     eax, 8007000Eh
0x1800061cd  mov     rcx, [rbp+40h+var_38]
0x1800061d1  xor     rcx, rbp; StackCookie
0x1800061d4  call    __security_check_cookie
0x1800061d9  lea     rsp, [rbp+18h]
0x1800061dd  pop     r15
0x1800061df  pop     r14
0x1800061e1  pop     rdi
0x1800061e2  pop     rsi
0x1800061e3  pop     rbx
0x1800061e4  pop     rbp
0x1800061e5  retn
```
