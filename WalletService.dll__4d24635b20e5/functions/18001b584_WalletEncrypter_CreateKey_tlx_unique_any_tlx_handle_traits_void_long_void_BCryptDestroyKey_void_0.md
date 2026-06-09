# WalletEncrypter::CreateKey(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)

- ea: `0x18001b584`
- end: `0x18001b759`
- name: `?CreateKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011924`
- `0x18001be00`

## callees

- `0x18001b310`
- `0x18001b584`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18001b6d5`
- `bcrypt!BCryptGenRandom` at `0x18001b6d5`
- `bcrypt!BCryptGetProperty` at `0x18001b601`
- `bcrypt!BCryptGetProperty` at `0x18001b6a7`
- `bcrypt!BCryptGetProperty` at `0x18001b601`
- `bcrypt!BCryptGetProperty` at `0x18001b6a7`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001b717`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001b717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b61b`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001b640`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001b640`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::CreateKey(__int64 a1, void **a2)
{
  BCRYPT_HANDLE v4; // rcx
  ULONG *v5; // r14
  NTSTATUS Property; // eax
  unsigned int v7; // ecx
  LPVOID v8; // rax
  LPVOID v9; // rbx
  size_t v10; // rdi
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  ULONG v13; // ebx
  UCHAR *v14; // rdi
  void **v15; // rax
  int v16; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-BCh] BYREF
  LPMALLOC ppMalloc; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR pbBuffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(pbBuffer, 0, sizeof(pbBuffer));
  v4 = *(BCRYPT_HANDLE *)a1;
  v5 = (ULONG *)(a1 + 8);
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(v4, L"ObjectLength", (PUCHAR)(a1 + 8), 4u, &pcbResult, 0);
  v7 = Property | 0x10000000;
  if ( Property >= 0 )
  {
    v8 = CoTaskMemAlloc(*v5);
    *(_QWORD *)(a1 + 16) = v8;
    v9 = v8;
    if ( v8 )
    {
      v10 = 0;
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v9);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(*(void **)(a1 + 16), 0, v10);
      v11 = BCryptGetProperty(*(BCRYPT_HANDLE *)a1, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
      v7 = v11 | 0x10000000;
      if ( v11 >= 0 )
      {
        if ( *(_DWORD *)pbOutput == 16 )
        {
          v12 = BCryptGenRandom(0, pbBuffer, 0x100u, 2u);
          v7 = v12 | 0x10000000;
          if ( v12 >= 0 )
          {
            v13 = *v5;
            v14 = *(UCHAR **)(a1 + 16);
            v15 = tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long BCryptDestroyKey(void *),0>>(a2);
            v16 = BCryptGenerateSymmetricKey(*(BCRYPT_ALG_HANDLE *)a1, v15, v14, v13, pbBuffer, 0x100u, 0) | 0x10000000;
            v7 = 0;
            if ( v16 < 0 )
              return (unsigned int)v16;
          }
        }
        else
        {
          return (unsigned int)-2147418113;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001b584  mov     [rsp-8+arg_10], rbx
0x18001b589  mov     [rsp-8+arg_18], rsi
0x18001b58e  push    rbp
0x18001b58f  push    rdi
0x18001b590  push    r13
0x18001b592  push    r14
0x18001b594  push    r15
0x18001b596  lea     rbp, [rsp-60h]
0x18001b59b  sub     rsp, 160h
0x18001b5a2  mov     rax, cs:__security_cookie
0x18001b5a9  xor     rax, rsp
0x18001b5ac  mov     [rbp+80h+var_30], rax
0x18001b5b0  mov     r15, rdx
0x18001b5b3  mov     rsi, rcx
0x18001b5b6  xor     edx, edx; Val
0x18001b5b8  lea     rcx, [rsp+180h+pbBuffer]; void *
0x18001b5bd  mov     r8d, 100h; Size
0x18001b5c3  call    memset_0
0x18001b5c8  mov     rcx, [rsi]; hObject
0x18001b5cb  lea     rax, [rsp+180h+var_140]
0x18001b5d0  lea     r14, [rsi+8]
0x18001b5d4  mov     [rsp+180h+dwFlags], 0; dwFlags
0x18001b5dc  mov     r8, r14; pbOutput
0x18001b5df  mov     [rsp+180h+pcbResult], rax; pcbResult
0x18001b5e4  mov     r9d, 4; cbOutput
0x18001b5ea  mov     dword ptr [rsp+180h+pbOutput], 0
0x18001b5f2  lea     rdx, pszProperty; "ObjectLength"
0x18001b5f9  mov     [rsp+180h+var_140], 0
0x18001b601  call    cs:__imp_BCryptGetProperty
0x18001b607  mov     ecx, eax
0x18001b609  mov     r13d, 10000000h
0x18001b60f  or      ecx, r13d
0x18001b612  jl      loc_18001B72F
0x18001b618  mov     ecx, [r14]; cb
0x18001b61b  call    cs:__imp_CoTaskMemAlloc
0x18001b621  mov     [rsi+10h], rax
0x18001b625  mov     rbx, rax
0x18001b628  test    rax, rax
0x18001b62b  jz      loc_18001B72A
0x18001b631  xor     edi, edi
0x18001b633  lea     rdx, [rsp+180h+ppMalloc]; ppMalloc
0x18001b638  mov     [rsp+180h+ppMalloc], rdi
0x18001b63d  lea     ecx, [rdi+1]; dwMemContext
0x18001b640  call    cs:__imp_CoGetMalloc
0x18001b646  test    eax, eax
0x18001b648  js      short loc_18001B672
0x18001b64a  mov     rcx, [rsp+180h+ppMalloc]
0x18001b64f  mov     rdx, rbx
0x18001b652  mov     rax, [rcx]
0x18001b655  mov     rax, [rax+30h]
0x18001b659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b65e  mov     rcx, [rsp+180h+ppMalloc]
0x18001b663  mov     rdi, rax
0x18001b666  mov     rax, [rcx]
0x18001b669  mov     rax, [rax+10h]
0x18001b66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b672  mov     rcx, [rsi+10h]; void *
0x18001b676  mov     r8, rdi; Size
0x18001b679  xor     edx, edx; Val
0x18001b67b  call    memset_0
0x18001b680  mov     rcx, [rsi]; hObject
0x18001b683  lea     rax, [rsp+180h+var_140]
0x18001b688  mov     [rsp+180h+dwFlags], 0; dwFlags
0x18001b690  lea     r8, [rsp+180h+pbOutput]; pbOutput
0x18001b695  mov     r9d, 4; cbOutput
0x18001b69b  mov     [rsp+180h+pcbResult], rax; pcbResult
0x18001b6a0  lea     rdx, aBlocklength; "BlockLength"
0x18001b6a7  call    cs:__imp_BCryptGetProperty
0x18001b6ad  mov     ecx, eax
0x18001b6af  or      ecx, r13d
0x18001b6b2  jl      short loc_18001B72F
0x18001b6b4  cmp     dword ptr [rsp+180h+pbOutput], 10h
0x18001b6b9  jz      short loc_18001B6C2
0x18001b6bb  mov     ecx, 8000FFFFh
0x18001b6c0  jmp     short loc_18001B72F
0x18001b6c2  mov     r9d, 2; dwFlags
0x18001b6c8  lea     rdx, [rsp+180h+pbBuffer]; pbBuffer
0x18001b6cd  mov     r8d, 100h; cbBuffer
0x18001b6d3  xor     ecx, ecx; hAlgorithm
0x18001b6d5  call    cs:__imp_BCryptGenRandom
0x18001b6db  mov     ecx, eax
0x18001b6dd  or      ecx, r13d
0x18001b6e0  jl      short loc_18001B72F
0x18001b6e2  mov     ebx, [r14]
0x18001b6e5  mov     rcx, r15
0x18001b6e8  mov     rdi, [rsi+10h]
0x18001b6ec  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001b6f1  lea     rcx, [rsp+180h+pbBuffer]
0x18001b6f6  mov     [rsp+180h+var_150], 0; dwFlags
0x18001b6fe  mov     [rsp+180h+dwFlags], 100h; cbSecret
0x18001b706  mov     r9d, ebx; cbKeyObject
0x18001b709  mov     [rsp+180h+pcbResult], rcx; pbSecret
0x18001b70e  mov     r8, rdi; pbKeyObject
0x18001b711  mov     rcx, [rsi]; hAlgorithm
0x18001b714  mov     rdx, rax; phKey
0x18001b717  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001b71d  or      eax, r13d
0x18001b720  mov     ecx, 0
0x18001b725  cmovl   ecx, eax
0x18001b728  jmp     short loc_18001B72F
0x18001b72a  mov     ecx, 8007000Eh
0x18001b72f  mov     eax, ecx
0x18001b731  mov     rcx, [rbp+80h+var_30]
0x18001b735  xor     rcx, rsp; StackCookie
0x18001b738  call    __security_check_cookie
0x18001b73d  lea     r11, [rsp+180h+var_20]
0x18001b745  mov     rbx, [r11+40h]
0x18001b749  mov     rsi, [r11+48h]
0x18001b74d  mov     rsp, r11
0x18001b750  pop     r15
0x18001b752  pop     r14
0x18001b754  pop     r13
0x18001b756  pop     rdi
0x18001b757  pop     rbp
0x18001b758  retn
```
