# DllGetActivationFactory

- ea: `0x180006bd0`
- end: `0x180006dac`
- name: `DllGetActivationFactory`
- size: `476`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002c40`
- `0x180006bd0`
- `0x180165920`
- `0x180172640`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006c0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006c0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006c46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006c46`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006cfb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006cfb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006d77`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006d77`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
{
  PCWSTR StringRawBuffer; // rbp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v14; // [rsp+34h] [rbp-54h] BYREF
  _OWORD v15[2]; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+58h] [rbp-30h]
  __int16 v17; // [rsp+5Ch] [rbp-2Ch]

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1801AB9C8 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v15[0] = xmmword_180182E30;
    v15[1] = xmmword_180182E40;
    v16 = 6553673;
    v17 = 0;
    RoOriginateErrorW(2147942487LL, 18, v15);
    return 2147942487LL;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)&qword_1801AB9C0 + 40LL))(&qword_1801AB9C0) + 8;
    v6 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)&qword_1801AB9C0 + 48LL))(&qword_1801AB9C0);
    if ( v5 >= v6 )
    {
LABEL_11:
      RoOriginateError(2147746065LL, string);
      return 2147746065LL;
    }
    else
    {
      while ( 1 )
      {
        if ( *(_QWORD *)v5 )
        {
          v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
          v8 = (unsigned __int16 *)StringRawBuffer;
          v9 = v7 - (_QWORD)StringRawBuffer;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v8 + v9);
            v11 = *v8 - v10;
            if ( v11 )
              break;
            ++v8;
          }
          while ( v10 );
          if ( !v11 )
            break;
        }
        v5 += 8LL;
        if ( v5 >= v6 )
          goto LABEL_11;
      }
      v14 = 1;
      return sub_180002C40((int)&qword_1801AB9C0, (int)&v14, (int)&byte_180183250, *(_QWORD *)v5, Ptr);
    }
  }
}

```

## disassembly

```asm
0x180006bd0  mov     [rsp+arg_10], rbx
0x180006bd5  mov     [rsp+arg_18], rbp
0x180006bda  push    rsi
0x180006bdb  push    rdi
0x180006bdc  push    r14
0x180006bde  sub     rsp, 70h
0x180006be2  mov     rax, cs:__security_cookie
0x180006be9  xor     rax, rsp
0x180006bec  mov     [rsp+88h+var_28], rax
0x180006bf1  mov     r14, rdx
0x180006bf4  mov     rsi, rcx
0x180006bf7  xor     r9d, r9d; Context
0x180006bfa  xor     r8d, r8d; Parameter
0x180006bfd  lea     rdx, InitFn; InitFn
0x180006c04  lea     rcx, InitOnce; InitOnce
0x180006c0b  call    cs:InitOnceExecuteOnce
0x180006c12  nop     dword ptr [rax+rax+00h]
0x180006c17  mov     cs:byte_1801AB9C8, 1
0x180006c1e  xor     eax, eax
0x180006c20  mov     [r14], rax
0x180006c23  mov     [rsp+88h+hasEmbedNull], eax
0x180006c27  mov     rcx, rsi; string
0x180006c2a  call    cs:WindowsIsStringEmpty
0x180006c31  nop     dword ptr [rax+rax+00h]
0x180006c36  test    eax, eax
0x180006c38  jnz     loc_180006D3A
0x180006c3e  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180006c43  mov     rcx, rsi; string
0x180006c46  call    cs:WindowsStringHasEmbeddedNull
0x180006c4d  nop     dword ptr [rax+rax+00h]
0x180006c52  test    eax, eax
0x180006c54  js      loc_180006D3A
0x180006c5a  cmp     [rsp+88h+hasEmbedNull], 1
0x180006c5f  jz      loc_180006D3A
0x180006c65  xor     edx, edx; length
0x180006c67  mov     rcx, rsi; string
0x180006c6a  call    cs:WindowsGetStringRawBuffer
0x180006c71  nop     dword ptr [rax+rax+00h]
0x180006c76  mov     rbp, rax
0x180006c79  mov     rcx, cs:qword_1801AB9C0
0x180006c80  mov     rax, [rcx+28h]
0x180006c84  lea     rcx, qword_1801AB9C0
0x180006c8b  call    cs:__guard_dispatch_icall_fptr
0x180006c91  lea     rbx, [rax+8]
0x180006c95  mov     rcx, cs:qword_1801AB9C0
0x180006c9c  mov     rax, [rcx+30h]
0x180006ca0  lea     rcx, qword_1801AB9C0
0x180006ca7  call    cs:__guard_dispatch_icall_fptr
0x180006cad  mov     rdi, rax
0x180006cb0  cmp     rbx, rax
0x180006cb3  jnb     short loc_180006CF3
0x180006cb5  mov     rax, [rbx]
0x180006cb8  test    rax, rax
0x180006cbb  jz      short loc_180006CEA
0x180006cbd  mov     rax, [rax+8]
0x180006cc1  call    cs:__guard_dispatch_icall_fptr
0x180006cc7  mov     rcx, rbp
0x180006cca  sub     rax, rbp
0x180006ccd  nop     dword ptr [rax]
0x180006cd0  movzx   r8d, word ptr [rcx]
0x180006cd4  movzx   edx, word ptr [rcx+rax]
0x180006cd8  sub     r8d, edx
0x180006cdb  jnz     short loc_180006CE5
0x180006cdd  add     rcx, 2
0x180006ce1  test    edx, edx
0x180006ce3  jnz     short loc_180006CD0
0x180006ce5  test    r8d, r8d
0x180006ce8  jz      short loc_180006D0F
0x180006cea  add     rbx, 8
0x180006cee  cmp     rbx, rdi
0x180006cf1  jb      short loc_180006CB5
0x180006cf3  mov     rdx, rsi
0x180006cf6  mov     ecx, 80040111h
0x180006cfb  call    cs:RoOriginateError
0x180006d02  nop     dword ptr [rax+rax+00h]
0x180006d07  nop
0x180006d08  mov     eax, 80040111h
0x180006d0d  jmp     short loc_180006D89
0x180006d0f  mov     [rsp+88h+var_54], 1
0x180006d17  mov     [rsp+88h+Ptr], r14; Ptr
0x180006d1c  mov     r9, [rbx]; int
0x180006d1f  lea     r8, byte_180183250; int
0x180006d26  lea     rdx, [rsp+88h+var_54]; int
0x180006d2b  lea     rcx, qword_1801AB9C0; int
0x180006d32  call    sub_180002C40
0x180006d37  nop
0x180006d38  jmp     short loc_180006D89
0x180006d3a  movups  xmm0, cs:xmmword_180182E30
0x180006d41  movups  [rsp+88h+var_50], xmm0
0x180006d46  movups  xmm1, cs:xmmword_180182E40
0x180006d4d  movups  [rsp+88h+var_40], xmm1
0x180006d52  mov     eax, cs:dword_180182E50
0x180006d58  mov     [rsp+88h+var_30], eax
0x180006d5c  movzx   eax, cs:word_180182E54
0x180006d63  mov     [rsp+88h+var_2C], ax
0x180006d68  lea     r8, [rsp+88h+var_50]
0x180006d6d  mov     edx, 12h
0x180006d72  mov     ecx, 80070057h
0x180006d77  call    cs:RoOriginateErrorW
0x180006d7e  nop     dword ptr [rax+rax+00h]
0x180006d83  nop
0x180006d84  mov     eax, 80070057h
0x180006d89  mov     rcx, [rsp+88h+var_28]
0x180006d8e  xor     rcx, rsp; StackCookie
0x180006d91  call    __security_check_cookie
0x180006d96  lea     r11, [rsp+88h+var_18]
0x180006d9b  mov     rbx, [r11+30h]
0x180006d9f  mov     rbp, [r11+38h]
0x180006da3  mov     rsp, r11
0x180006da6  pop     r14
0x180006da8  pop     rdi
0x180006da9  pop     rsi
0x180006daa  retn
```
