# CFilterMapiFps::GetText(ulong *,wchar_t *)

- ea: `0x18001edb0`
- end: `0x18001ef86`
- name: `?GetText@CFilterMapiFps@@UEAAJPEAKPEA_W@Z`
- size: `470`
- prototype: `__int64 __fastcall(CFilterMapiFps *this, unsigned int *, wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000306c`
- `0x1800113ac`
- `0x1800113ec`
- `0x18001edb0`
- `0x18002243c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001ef36`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001ef36`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ee55`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001eed8`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001eed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eeb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eeb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ee5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ee5e`
- `PROPSYS!PropVariantToString` at `0x18001ee04`
- `PROPSYS!PropVariantToString` at `0x18001ee04`

## pseudocode

```c
__int64 __fastcall CFilterMapiFps::GetText(CFilterMapiFps *this, unsigned int *a2, wchar_t *a3)
{
  __int64 v4; // rcx
  wchar_t *v5; // rsi
  PROPVARIANT *v8; // rbp
  int v9; // ebx
  HRESULT v10; // eax
  __int64 v11; // rax
  LPVOID v12; // rax
  LPVOID v13; // rbx
  size_t v14; // rbp
  UINT v15; // ebp
  LPMALLOC ppMalloc; // [rsp+60h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 3);
  v5 = a3;
  if ( !v4 )
    return 2147500035LL;
  if ( *((_DWORD *)this + 21) )
  {
    v8 = (PROPVARIANT *)*((_QWORD *)this + 9);
    if ( v8 )
    {
      *((_QWORD *)this + 9) = 0;
      v9 = 0;
      if ( *a2 )
      {
        v10 = PropVariantToString(v8, a3, *a2);
        v9 = v10;
        if ( v10 == -2147024774 )
        {
          CLogger::Info(L"CMapi2RowFilter::CFilterMapiFps: Skipping property as too long: %s", v5);
          *v5 = 0;
        }
        else
        {
          if ( v10 >= 0 )
          {
            v11 = -1;
            do
              ++v11;
            while ( v5[v11] );
            *a2 = v11;
            goto LABEL_14;
          }
          CLogger::Info(v10, L"CMapi2RowFilter::CFilterMapiFps: property could not be converted to text");
        }
        v9 = -2147215615;
      }
LABEL_14:
      PropVariantClear(v8);
      CoTaskMemFree(v8);
      goto LABEL_17;
    }
    v9 = -2147215615;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
  }
LABEL_17:
  if ( v9 >= 0 && *((_DWORD *)this + 28) && *((_DWORD *)this + 30) && !*((_DWORD *)this + 29) )
  {
    if ( *((_QWORD *)this + 13) )
      goto LABEL_29;
    v12 = CoTaskMemAlloc(2LL * (unsigned int)dword_180059280);
    *((_QWORD *)this + 13) = v12;
    v13 = v12;
    if ( v12 )
    {
      ppMalloc = 0;
      v14 = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v14 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v13);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(*((void **)this + 13), 0, v14);
      v9 = 0;
    }
    else
    {
      v9 = -2147024882;
    }
    if ( v9 >= 0 && *((_QWORD *)this + 13) )
    {
LABEL_29:
      v15 = *a2;
      if ( *a2 )
      {
        while ( (unsigned int)_o_iswspace(*v5) )
        {
          ++v5;
          if ( !--v15 )
            goto LABEL_35;
        }
        v9 = StringCchCatNW(*((wchar_t **)this + 13), (unsigned int)dword_180059280, v5, v15);
        if ( v9 == -2147024774 )
        {
          v9 = 0;
          *((_DWORD *)this + 29) = 1;
        }
      }
    }
  }
LABEL_35:
  *((_DWORD *)this + 28) = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001edb0  push    rbx
0x18001edb2  push    rbp
0x18001edb3  push    rsi
0x18001edb4  push    rdi
0x18001edb5  push    r14
0x18001edb7  push    r15
0x18001edb9  sub     rsp, 28h
0x18001edbd  mov     rdi, rcx
0x18001edc0  xor     r15d, r15d
0x18001edc3  mov     rcx, [rcx+18h]
0x18001edc7  mov     rsi, r8
0x18001edca  mov     r14, rdx
0x18001edcd  test    rcx, rcx
0x18001edd0  jnz     short loc_18001EDDC
0x18001edd2  mov     eax, 80004003h
0x18001edd7  jmp     loc_18001EF79
0x18001eddc  cmp     [rdi+54h], r15d
0x18001ede0  jz      loc_18001EE6D
0x18001ede6  mov     rbp, [rdi+48h]
0x18001edea  test    rbp, rbp
0x18001eded  jz      short loc_18001EE66
0x18001edef  mov     [rdi+48h], r15
0x18001edf3  mov     ebx, r15d
0x18001edf6  mov     r8d, [rdx]; cch
0x18001edf9  test    r8d, r8d
0x18001edfc  jz      short loc_18001EE52
0x18001edfe  mov     rdx, rsi; psz
0x18001ee01  mov     rcx, rbp; propvar
0x18001ee04  call    cs:__imp_PropVariantToString
0x18001ee0a  mov     ebx, eax
0x18001ee0c  cmp     eax, 8007007Ah
0x18001ee11  jnz     short loc_18001EE28
0x18001ee13  mov     rdx, rsi
0x18001ee16  lea     rcx, aCmapi2rowfilte_2; "CMapi2RowFilter::CFilterMapiFps: Skippi"...
0x18001ee1d  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18001ee22  mov     [rsi], r15w
0x18001ee26  jmp     short loc_18001EE3A
0x18001ee28  test    eax, eax
0x18001ee2a  jns     short loc_18001EE41
0x18001ee2c  lea     rdx, aCmapi2rowfilte; "CMapi2RowFilter::CFilterMapiFps: proper"...
0x18001ee33  mov     ecx, eax; int
0x18001ee35  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18001ee3a  mov     ebx, 80041701h
0x18001ee3f  jmp     short loc_18001EE52
0x18001ee41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee45  inc     rax
0x18001ee48  cmp     [rsi+rax*2], r15w
0x18001ee4d  jnz     short loc_18001EE45
0x18001ee4f  mov     [r14], eax
0x18001ee52  mov     rcx, rbp; pvar
0x18001ee55  call    cs:__imp_PropVariantClear
0x18001ee5b  mov     rcx, rbp; pv
0x18001ee5e  call    cs:__imp_CoTaskMemFree
0x18001ee64  jmp     short loc_18001EE7B
0x18001ee66  mov     ebx, 80041701h
0x18001ee6b  jmp     short loc_18001EE7B
0x18001ee6d  mov     rax, [rcx]
0x18001ee70  mov     rax, [rax+28h]
0x18001ee74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee79  mov     ebx, eax
0x18001ee7b  test    ebx, ebx
0x18001ee7d  js      loc_18001EF73
0x18001ee83  cmp     [rdi+70h], r15d
0x18001ee87  jz      loc_18001EF73
0x18001ee8d  cmp     [rdi+78h], r15d
0x18001ee91  jz      loc_18001EF73
0x18001ee97  cmp     [rdi+74h], r15d
0x18001ee9b  jnz     loc_18001EF73
0x18001eea1  cmp     [rdi+68h], r15
0x18001eea5  jnz     loc_18001EF2C
0x18001eeab  mov     ecx, cs:dword_180059280
0x18001eeb1  add     rcx, rcx; cb
0x18001eeb4  call    cs:__imp_CoTaskMemAlloc
0x18001eeba  mov     [rdi+68h], rax
0x18001eebe  mov     rbx, rax
0x18001eec1  test    rax, rax
0x18001eec4  jz      short loc_18001EF1D
0x18001eec6  lea     rdx, [rsp+58h+ppMalloc]; ppMalloc
0x18001eecb  mov     [rsp+58h+ppMalloc], r15
0x18001eed0  mov     ecx, 1; dwMemContext
0x18001eed5  mov     rbp, r15
0x18001eed8  call    cs:__imp_CoGetMalloc
0x18001eede  test    eax, eax
0x18001eee0  js      short loc_18001EF0A
0x18001eee2  mov     rcx, [rsp+58h+ppMalloc]
0x18001eee7  mov     rdx, rbx
0x18001eeea  mov     rax, [rcx]
0x18001eeed  mov     rax, [rax+30h]
0x18001eef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eef6  mov     rcx, [rsp+58h+ppMalloc]
0x18001eefb  mov     rbp, rax
0x18001eefe  mov     rdx, [rcx]
0x18001ef01  mov     rax, [rdx+10h]
0x18001ef05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef0a  mov     rcx, [rdi+68h]; void *
0x18001ef0e  mov     r8, rbp; Size
0x18001ef11  xor     edx, edx; Val
0x18001ef13  call    memset_0
0x18001ef18  mov     ebx, r15d
0x18001ef1b  jmp     short loc_18001EF22
0x18001ef1d  mov     ebx, 8007000Eh
0x18001ef22  test    ebx, ebx
0x18001ef24  js      short loc_18001EF73
0x18001ef26  cmp     [rdi+68h], r15
0x18001ef2a  jz      short loc_18001EF73
0x18001ef2c  mov     ebp, [r14]
0x18001ef2f  test    ebp, ebp
0x18001ef31  jz      short loc_18001EF73
0x18001ef33  movzx   ecx, word ptr [rsi]
0x18001ef36  call    cs:__imp__o_iswspace
0x18001ef3c  test    eax, eax
0x18001ef3e  jz      short loc_18001EF4B
0x18001ef40  add     rsi, 2
0x18001ef44  add     ebp, 0FFFFFFFFh
0x18001ef47  jnz     short loc_18001EF33
0x18001ef49  jmp     short loc_18001EF73
0x18001ef4b  mov     edx, cs:dword_180059280; unsigned __int64
0x18001ef51  mov     r8, rsi; wchar_t *
0x18001ef54  mov     rcx, [rdi+68h]; wchar_t *
0x18001ef58  mov     r9d, ebp; unsigned __int64
0x18001ef5b  call    ?StringCchCatNW@@YAJPEA_W_KPEB_W1@Z; StringCchCatNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18001ef60  mov     ebx, eax
0x18001ef62  cmp     eax, 8007007Ah
0x18001ef67  jnz     short loc_18001EF73
0x18001ef69  mov     ebx, r15d
0x18001ef6c  mov     dword ptr [rdi+74h], 1
0x18001ef73  mov     [rdi+70h], r15d
0x18001ef77  mov     eax, ebx
0x18001ef79  add     rsp, 28h
0x18001ef7d  pop     r15
0x18001ef7f  pop     r14
0x18001ef81  pop     rdi
0x18001ef82  pop     rsi
0x18001ef83  pop     rbp
0x18001ef84  pop     rbx
0x18001ef85  retn
```
