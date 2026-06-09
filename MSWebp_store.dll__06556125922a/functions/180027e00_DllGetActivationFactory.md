# DllGetActivationFactory

- ea: `0x180027e00`
- end: `0x180027fd7`
- name: `DllGetActivationFactory`
- size: `471`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001740`
- `0x180027e00`
- `0x18002804c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027e42`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180027e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180027e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180027e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180027e67`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180027fa6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180027fa6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027f34`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180027f34`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // r14
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v13; // r9
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v16; // [rsp+34h] [rbp-54h] BYREF
  _OWORD v17[2]; // [rsp+38h] [rbp-50h] BYREF
  int v18; // [rsp+58h] [rbp-30h]
  __int16 v19; // [rsp+5Ch] [rbp-2Ch]

  *a2 = 0;
  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1800464A0 = 1;
  *a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v18 = 6553673;
    v12 = -2147024809;
    v19 = 0;
    v17[0] = xmmword_18003E010;
    v17[1] = xmmword_18003E020;
    RoOriginateErrorW(2147942487LL, 18, v17);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(__int64 *))(qword_180046498 + 40))(&qword_180046498) + 8;
    v6 = (*(__int64 (__fastcall **)(__int64 *))(qword_180046498 + 48))(&qword_180046498);
    if ( v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
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
      v13 = *(_QWORD *)v5;
      v16 = 1;
      return (unsigned int)sub_18002804C((unsigned int)&qword_180046498, (unsigned int)&v16, v10, v13, (__int64)a2);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180027e00  mov     [rsp+arg_10], rbx
0x180027e05  mov     [rsp+arg_18], rbp
0x180027e0a  push    rsi
0x180027e0b  push    rdi
0x180027e0c  push    r14
0x180027e0e  sub     rsp, 70h
0x180027e12  mov     rax, cs:__security_cookie
0x180027e19  xor     rax, rsp
0x180027e1c  mov     [rsp+88h+var_28], rax
0x180027e21  mov     rsi, rdx
0x180027e24  mov     qword ptr [rdx], 0
0x180027e2b  mov     rdi, rcx
0x180027e2e  lea     rdx, InitFn; InitFn
0x180027e35  lea     rcx, InitOnce; InitOnce
0x180027e3c  xor     r9d, r9d; Context
0x180027e3f  xor     r8d, r8d; Parameter
0x180027e42  call    cs:InitOnceExecuteOnce
0x180027e49  nop     dword ptr [rax+rax+00h]
0x180027e4e  mov     cs:byte_1800464A0, 1
0x180027e55  mov     rcx, rdi; string
0x180027e58  mov     qword ptr [rsi], 0
0x180027e5f  mov     [rsp+88h+hasEmbedNull], 0
0x180027e67  call    cs:WindowsIsStringEmpty
0x180027e6e  nop     dword ptr [rax+rax+00h]
0x180027e73  test    eax, eax
0x180027e75  jnz     loc_180027F67
0x180027e7b  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180027e80  mov     rcx, rdi; string
0x180027e83  call    cs:WindowsStringHasEmbeddedNull
0x180027e8a  nop     dword ptr [rax+rax+00h]
0x180027e8f  test    eax, eax
0x180027e91  js      loc_180027F67
0x180027e97  cmp     [rsp+88h+hasEmbedNull], 1
0x180027e9c  jz      loc_180027F67
0x180027ea2  xor     edx, edx; length
0x180027ea4  mov     rcx, rdi; string
0x180027ea7  call    cs:WindowsGetStringRawBuffer
0x180027eae  nop     dword ptr [rax+rax+00h]
0x180027eb3  mov     rcx, cs:qword_180046498
0x180027eba  mov     r14, rax
0x180027ebd  mov     rax, [rcx+28h]
0x180027ec1  lea     rcx, qword_180046498
0x180027ec8  call    j__guard_dispatch_icall
0x180027ecd  mov     rcx, cs:qword_180046498
0x180027ed4  lea     rbx, [rax+8]
0x180027ed8  mov     rax, [rcx+30h]
0x180027edc  lea     rcx, qword_180046498
0x180027ee3  call    j__guard_dispatch_icall
0x180027ee8  mov     rbp, rax
0x180027eeb  cmp     rbx, rax
0x180027eee  jnb     short loc_180027F2A
0x180027ef0  mov     rax, [rbx]
0x180027ef3  test    rax, rax
0x180027ef6  jz      short loc_180027F21
0x180027ef8  mov     rax, [rax+8]
0x180027efc  call    j__guard_dispatch_icall
0x180027f01  mov     rcx, r14
0x180027f04  sub     rax, r14
0x180027f07  movzx   edx, word ptr [rcx]
0x180027f0a  movzx   r8d, word ptr [rcx+rax]
0x180027f0f  sub     edx, r8d
0x180027f12  jnz     short loc_180027F1D
0x180027f14  add     rcx, 2
0x180027f18  test    r8d, r8d
0x180027f1b  jnz     short loc_180027F07
0x180027f1d  test    edx, edx
0x180027f1f  jz      short loc_180027F42
0x180027f21  add     rbx, 8
0x180027f25  cmp     rbx, rbp
0x180027f28  jb      short loc_180027EF0
0x180027f2a  mov     ebx, 80040111h
0x180027f2f  mov     rdx, rdi
0x180027f32  mov     ecx, ebx
0x180027f34  call    cs:RoOriginateError
0x180027f3b  nop     dword ptr [rax+rax+00h]
0x180027f40  jmp     short loc_180027FB2
0x180027f42  mov     r9, [rbx]
0x180027f45  lea     rdx, [rsp+88h+var_54]
0x180027f4a  lea     rcx, qword_180046498
0x180027f51  mov     [rsp+88h+var_54], 1
0x180027f59  mov     [rsp+88h+var_68], rsi
0x180027f5e  call    sub_18002804C
0x180027f63  mov     ebx, eax
0x180027f65  jmp     short loc_180027FB2
0x180027f67  mov     eax, cs:dword_18003E030
0x180027f6d  lea     r8, [rsp+88h+var_50]
0x180027f72  movups  xmm0, cs:xmmword_18003E010
0x180027f79  mov     [rsp+88h+var_30], eax
0x180027f7d  mov     ebx, 80070057h
0x180027f82  movups  xmm1, cs:xmmword_18003E020
0x180027f89  movzx   eax, cs:word_18003E034
0x180027f90  mov     edx, 12h
0x180027f95  mov     ecx, ebx
0x180027f97  mov     [rsp+88h+var_2C], ax
0x180027f9c  movups  [rsp+88h+var_50], xmm0
0x180027fa1  movups  [rsp+88h+var_40], xmm1
0x180027fa6  call    cs:RoOriginateErrorW
0x180027fad  nop     dword ptr [rax+rax+00h]
0x180027fb2  mov     eax, ebx
0x180027fb4  mov     rcx, [rsp+88h+var_28]
0x180027fb9  xor     rcx, rsp; StackCookie
0x180027fbc  call    __security_check_cookie
0x180027fc1  lea     r11, [rsp+88h+var_18]
0x180027fc6  mov     rbx, [r11+30h]
0x180027fca  mov     rbp, [r11+38h]
0x180027fce  mov     rsp, r11
0x180027fd1  pop     r14
0x180027fd3  pop     rdi
0x180027fd4  pop     rsi
0x180027fd5  retn
```
