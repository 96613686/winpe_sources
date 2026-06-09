# DllGetActivationFactory

- ea: `0x18013c0e0`
- end: `0x18013c2b4`
- name: `DllGetActivationFactory`
- size: `468`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18013b940`
- `0x18013c0e0`
- `0x18017e9e0`
- `0x1801f9250`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18013c15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18013c15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18013c140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18013c140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013c180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013c180`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18013c282`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18013c282`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18013c210`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18013c210`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18013c11b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18013c11b`

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
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h] BYREF
  _OWORD v16[2]; // [rsp+38h] [rbp-50h] BYREF
  int v17; // [rsp+58h] [rbp-30h]
  __int16 v18; // [rsp+5Ch] [rbp-2Ch]

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_180270498 = 1;
  *a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v16[0] = xmmword_1802250A8;
    v16[1] = xmmword_1802250B8;
    v17 = 6553673;
    v18 = 0;
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, v16);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(__int64 *))(qword_180270490 + 40))(&qword_180270490) + 8;
    v6 = (*(__int64 (__fastcall **)(__int64 *))(qword_180270490 + 48))(&qword_180270490);
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
      v15 = 1;
      return (unsigned int)sub_18013B940(
                             (unsigned int)&qword_180270490,
                             (unsigned int)&v15,
                             v10,
                             *(_QWORD *)v5,
                             (__int64)a2);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18013c0e0  mov     [rsp+arg_10], rbx
0x18013c0e5  mov     [rsp+arg_18], rbp
0x18013c0ea  push    rsi
0x18013c0eb  push    rdi
0x18013c0ec  push    r14
0x18013c0ee  sub     rsp, 70h
0x18013c0f2  mov     rax, cs:__security_cookie
0x18013c0f9  xor     rax, rsp
0x18013c0fc  mov     [rsp+88h+var_28], rax
0x18013c101  mov     rsi, rdx
0x18013c104  mov     rdi, rcx
0x18013c107  xor     r9d, r9d; Context
0x18013c10a  xor     r8d, r8d; Parameter
0x18013c10d  lea     rdx, InitFn; InitFn
0x18013c114  lea     rcx, InitOnce; InitOnce
0x18013c11b  call    cs:InitOnceExecuteOnce
0x18013c122  nop     dword ptr [rax+rax+00h]
0x18013c127  mov     cs:byte_180270498, 1
0x18013c12e  mov     qword ptr [rsi], 0
0x18013c135  mov     [rsp+88h+hasEmbedNull], 0
0x18013c13d  mov     rcx, rdi; string
0x18013c140  call    cs:WindowsIsStringEmpty
0x18013c147  nop     dword ptr [rax+rax+00h]
0x18013c14c  test    eax, eax
0x18013c14e  jnz     loc_18013C243
0x18013c154  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18013c159  mov     rcx, rdi; string
0x18013c15c  call    cs:WindowsStringHasEmbeddedNull
0x18013c163  nop     dword ptr [rax+rax+00h]
0x18013c168  test    eax, eax
0x18013c16a  js      loc_18013C243
0x18013c170  cmp     [rsp+88h+hasEmbedNull], 1
0x18013c175  jz      loc_18013C243
0x18013c17b  xor     edx, edx; length
0x18013c17d  mov     rcx, rdi; string
0x18013c180  call    cs:WindowsGetStringRawBuffer
0x18013c187  nop     dword ptr [rax+rax+00h]
0x18013c18c  mov     r14, rax
0x18013c18f  mov     rcx, cs:qword_180270490
0x18013c196  mov     rax, [rcx+28h]
0x18013c19a  lea     rcx, qword_180270490
0x18013c1a1  call    cs:__guard_dispatch_icall_fptr
0x18013c1a7  lea     rbx, [rax+8]
0x18013c1ab  mov     rcx, cs:qword_180270490
0x18013c1b2  mov     rax, [rcx+30h]
0x18013c1b6  lea     rcx, qword_180270490
0x18013c1bd  call    cs:__guard_dispatch_icall_fptr
0x18013c1c3  mov     rbp, rax
0x18013c1c6  cmp     rbx, rax
0x18013c1c9  jnb     short loc_18013C206
0x18013c1cb  mov     rax, [rbx]
0x18013c1ce  test    rax, rax
0x18013c1d1  jz      short loc_18013C1FD
0x18013c1d3  mov     rax, [rax+8]
0x18013c1d7  call    cs:__guard_dispatch_icall_fptr
0x18013c1dd  mov     rcx, r14
0x18013c1e0  sub     rax, r14
0x18013c1e3  movzx   edx, word ptr [rcx]
0x18013c1e6  movzx   r8d, word ptr [rcx+rax]
0x18013c1eb  sub     edx, r8d
0x18013c1ee  jnz     short loc_18013C1F9
0x18013c1f0  add     rcx, 2
0x18013c1f4  test    r8d, r8d
0x18013c1f7  jnz     short loc_18013C1E3
0x18013c1f9  test    edx, edx
0x18013c1fb  jz      short loc_18013C21E
0x18013c1fd  add     rbx, 8
0x18013c201  cmp     rbx, rbp
0x18013c204  jb      short loc_18013C1CB
0x18013c206  mov     rdx, rdi
0x18013c209  mov     ebx, 80040111h
0x18013c20e  mov     ecx, ebx
0x18013c210  call    cs:RoOriginateError
0x18013c217  nop     dword ptr [rax+rax+00h]
0x18013c21c  jmp     short loc_18013C28F
0x18013c21e  mov     [rsp+88h+var_54], 1
0x18013c226  mov     [rsp+88h+var_68], rsi
0x18013c22b  mov     r9, [rbx]
0x18013c22e  lea     rdx, [rsp+88h+var_54]
0x18013c233  lea     rcx, qword_180270490
0x18013c23a  call    sub_18013B940
0x18013c23f  mov     ebx, eax
0x18013c241  jmp     short loc_18013C28F
0x18013c243  movups  xmm0, cs:xmmword_1802250A8
0x18013c24a  movups  [rsp+88h+var_50], xmm0
0x18013c24f  movups  xmm1, cs:xmmword_1802250B8
0x18013c256  movups  [rsp+88h+var_40], xmm1
0x18013c25b  mov     eax, cs:dword_1802250C8
0x18013c261  mov     [rsp+88h+var_30], eax
0x18013c265  movzx   eax, cs:word_1802250CC
0x18013c26c  mov     [rsp+88h+var_2C], ax
0x18013c271  lea     r8, [rsp+88h+var_50]
0x18013c276  mov     edx, 12h
0x18013c27b  mov     ebx, 80070057h
0x18013c280  mov     ecx, ebx
0x18013c282  call    cs:RoOriginateErrorW
0x18013c289  nop     dword ptr [rax+rax+00h]
0x18013c28e  nop
0x18013c28f  mov     eax, ebx
0x18013c291  mov     rcx, [rsp+88h+var_28]
0x18013c296  xor     rcx, rsp; StackCookie
0x18013c299  call    __security_check_cookie
0x18013c29e  lea     r11, [rsp+88h+var_18]
0x18013c2a3  mov     rbx, [r11+30h]
0x18013c2a7  mov     rbp, [r11+38h]
0x18013c2ab  mov     rsp, r11
0x18013c2ae  pop     r14
0x18013c2b0  pop     rdi
0x18013c2b1  pop     rsi
0x18013c2b2  retn
```
