# tpm12class::TPM_NV_DATA_PUBLIC::Decode(ushort *)

- ea: `0x1800b8ca0`
- end: `0x1800b8f36`
- name: `?Decode@TPM_NV_DATA_PUBLIC@tpm12class@@UEAAJPEAG@Z`
- size: `662`
- prototype: `int(tpm12class::TPM_NV_DATA_PUBLIC *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18002a750`
- `0x18003cce0`
- `0x18004c1e8`
- `0x1800764d0`
- `0x18007704c`
- `0x1800b8ca0`
- `0x1800bada0`
- `0x1800bb4d4`
- `0x1800bb7d0`
- `0x1800bbbf8`
- `0x1800c8010`

## string_xrefs

- `0x1800b8d89`: `pcrInfoRead.`
- `0x1800b8de0`: `pcrInfoWrite.`
- `0x1800b8e78`: `bReadSTClear`
- `0x1800b8e9f`: `bWriteSTClear`
- `0x1800b8ec6`: `bWriteDefine`

## pseudocode

```c
__int64 __fastcall tpm12class::TPM_NV_DATA_PUBLIC::Decode(tpm12class::TPM_NV_DATA_PUBLIC *this, unsigned __int16 *a2)
{
  int v4; // ebx
  unsigned __int8 v5; // r9
  unsigned __int8 v6; // r9
  unsigned __int8 v7; // r9
  unsigned __int16 v9; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v10[510]; // [rsp+32h] [rbp-226h] BYREF

  v9 = 0;
  v4 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( TraceEnabled() )
  {
    v4 = TraceIdentifier(a2, L"TPM_NV_DATA_PUBLIC");
    if ( v4 >= 0 )
    {
      v4 = TraceUINT16Value(
             a2,
             L"tag",
             *((_WORD *)this + 28),
             0,
             (struct TPM_SYMBOLTABLE_ENTRY *)&st_TPM_STRUCTURE_TAG,
             0);
      if ( v4 >= 0 )
      {
        v4 = TraceUINT32Value(a2, L"nvIndex", *((_DWORD *)this + 15), 0, 0, 0);
        if ( v4 >= 0 )
        {
          v4 = StringCchCopyW(&v9, 0x100u, a2);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(&v9, 0x100u, L"pcrInfoRead.");
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 8) + 40LL))(
                     *((_QWORD *)this + 8),
                     &v9);
              if ( v4 >= 0 )
              {
                v4 = StringCchCopyW(&v9, 0x100u, a2);
                if ( v4 >= 0 )
                {
                  v4 = StringCchCatW(&v9, 0x100u, L"pcrInfoWrite.");
                  if ( v4 >= 0 )
                  {
                    v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 9) + 40LL))(
                           *((_QWORD *)this + 9),
                           &v9);
                    if ( v4 >= 0 )
                    {
                      v4 = StringCchCopyW(&v9, 0x100u, a2);
                      if ( v4 >= 0 )
                      {
                        v4 = StringCchCatW(&v9, 0x100u, L"permission.");
                        if ( v4 >= 0 )
                        {
                          v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 10) + 40LL))(
                                 *((_QWORD *)this + 10),
                                 &v9);
                          if ( v4 >= 0 )
                          {
                            v4 = TraceUINT8Value(a2, L"bReadSTClear", *((_BYTE *)this + 88), v5, 0, 0);
                            if ( v4 >= 0 )
                            {
                              v4 = TraceUINT8Value(a2, L"bWriteSTClear", *((_BYTE *)this + 89), v6, 0, 0);
                              if ( v4 >= 0 )
                              {
                                v4 = TraceUINT8Value(a2, L"bWriteDefine", *((_BYTE *)this + 90), v7, 0, 0);
                                if ( v4 >= 0 )
                                  return (unsigned int)TraceUINT32Value(
                                                         a2,
                                                         L"dataSize",
                                                         *((_DWORD *)this + 23),
                                                         0,
                                                         0,
                                                         0);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b8ca0  mov     [rsp+arg_10], rbx
0x1800b8ca5  push    rsi
0x1800b8ca6  push    rdi
0x1800b8ca7  push    r14
0x1800b8ca9  sub     rsp, 240h
0x1800b8cb0  mov     rax, cs:__security_cookie
0x1800b8cb7  xor     rax, rsp
0x1800b8cba  mov     [rsp+258h+var_28], rax
0x1800b8cc2  mov     rdi, rdx
0x1800b8cc5  mov     rsi, rcx
0x1800b8cc8  xor     eax, eax
0x1800b8cca  lea     rcx, [rsp+258h+var_226]; void *
0x1800b8ccf  xor     edx, edx; Val
0x1800b8cd1  mov     [rsp+258h+var_228], ax
0x1800b8cd6  mov     r8d, 1FEh; Size
0x1800b8cdc  xor     ebx, ebx
0x1800b8cde  call    memset_0
0x1800b8ce3  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x1800b8ce8  test    al, al
0x1800b8cea  jz      loc_1800B8F0F
0x1800b8cf0  lea     rdx, aTpmNvDataPubli; "TPM_NV_DATA_PUBLIC"
0x1800b8cf7  mov     rcx, rdi; unsigned __int16 *
0x1800b8cfa  call    ?TraceIdentifier@@YAJPEAG0@Z; TraceIdentifier(ushort *,ushort *)
0x1800b8cff  mov     ebx, eax
0x1800b8d01  test    eax, eax
0x1800b8d03  js      loc_1800B8F0F
0x1800b8d09  movzx   r8d, word ptr [rsi+38h]; unsigned __int16
0x1800b8d0e  lea     rax, ?st_TPM_STRUCTURE_TAG@@3QBUTPM_SYMBOLTABLE_ENTRY@@B; TPM_SYMBOLTABLE_ENTRY const near * const st_TPM_STRUCTURE_TAG
0x1800b8d15  mov     [rsp+258h+var_230], 0; char
0x1800b8d1a  lea     rdx, aTag; "tag"
0x1800b8d21  xor     r9d, r9d; unsigned __int8
0x1800b8d24  mov     [rsp+258h+var_238], rax; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8d29  mov     rcx, rdi; unsigned __int16 *
0x1800b8d2c  call    ?TraceUINT16Value@@YAJPEAG0GEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT16Value(ushort *,ushort *,ushort,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8d31  mov     ebx, eax
0x1800b8d33  test    eax, eax
0x1800b8d35  js      loc_1800B8F0F
0x1800b8d3b  mov     r8d, [rsi+3Ch]; unsigned int
0x1800b8d3f  lea     rdx, aNvindex; "nvIndex"
0x1800b8d46  mov     [rsp+258h+var_230], 0; unsigned __int8
0x1800b8d4b  xor     r9d, r9d; unsigned __int8
0x1800b8d4e  mov     rcx, rdi; unsigned __int16 *
0x1800b8d51  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8d5a  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8d5f  mov     ebx, eax
0x1800b8d61  test    eax, eax
0x1800b8d63  js      loc_1800B8F0F
0x1800b8d69  mov     r14d, 100h
0x1800b8d6f  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8d74  mov     edx, r14d; unsigned __int64
0x1800b8d77  mov     r8, rdi; unsigned __int16 *
0x1800b8d7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8d7f  mov     ebx, eax
0x1800b8d81  test    eax, eax
0x1800b8d83  js      loc_1800B8F0F
0x1800b8d89  lea     r8, aPcrinforead; "pcrInfoRead."
0x1800b8d90  mov     edx, r14d; unsigned __int64
0x1800b8d93  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8d98  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b8d9d  mov     ebx, eax
0x1800b8d9f  test    eax, eax
0x1800b8da1  js      loc_1800B8F0F
0x1800b8da7  mov     rcx, [rsi+40h]
0x1800b8dab  lea     rdx, [rsp+258h+var_228]
0x1800b8db0  mov     rax, [rcx]
0x1800b8db3  mov     rax, [rax+28h]
0x1800b8db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8dbc  mov     ebx, eax
0x1800b8dbe  test    eax, eax
0x1800b8dc0  js      loc_1800B8F0F
0x1800b8dc6  mov     r8, rdi; unsigned __int16 *
0x1800b8dc9  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8dce  mov     edx, r14d; unsigned __int64
0x1800b8dd1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8dd6  mov     ebx, eax
0x1800b8dd8  test    eax, eax
0x1800b8dda  js      loc_1800B8F0F
0x1800b8de0  lea     r8, aPcrinfowrite; "pcrInfoWrite."
0x1800b8de7  mov     edx, r14d; unsigned __int64
0x1800b8dea  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8def  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b8df4  mov     ebx, eax
0x1800b8df6  test    eax, eax
0x1800b8df8  js      loc_1800B8F0F
0x1800b8dfe  mov     rcx, [rsi+48h]
0x1800b8e02  lea     rdx, [rsp+258h+var_228]
0x1800b8e07  mov     rax, [rcx]
0x1800b8e0a  mov     rax, [rax+28h]
0x1800b8e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e13  mov     ebx, eax
0x1800b8e15  test    eax, eax
0x1800b8e17  js      loc_1800B8F0F
0x1800b8e1d  mov     r8, rdi; unsigned __int16 *
0x1800b8e20  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8e25  mov     edx, r14d; unsigned __int64
0x1800b8e28  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b8e2d  mov     ebx, eax
0x1800b8e2f  test    eax, eax
0x1800b8e31  js      loc_1800B8F0F
0x1800b8e37  lea     r8, aPermission; "permission."
0x1800b8e3e  mov     edx, r14d; unsigned __int64
0x1800b8e41  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800b8e46  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b8e4b  mov     ebx, eax
0x1800b8e4d  test    eax, eax
0x1800b8e4f  js      loc_1800B8F0F
0x1800b8e55  mov     rcx, [rsi+50h]
0x1800b8e59  lea     rdx, [rsp+258h+var_228]
0x1800b8e5e  mov     rax, [rcx]
0x1800b8e61  mov     rax, [rax+28h]
0x1800b8e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e6a  mov     ebx, eax
0x1800b8e6c  test    eax, eax
0x1800b8e6e  js      loc_1800B8F0F
0x1800b8e74  mov     r8b, [rsi+58h]; unsigned __int8
0x1800b8e78  lea     rdx, aBreadstclear; "bReadSTClear"
0x1800b8e7f  mov     [rsp+258h+var_230], 0; char
0x1800b8e84  mov     rcx, rdi; unsigned __int16 *
0x1800b8e87  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8e90  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8e95  mov     ebx, eax
0x1800b8e97  test    eax, eax
0x1800b8e99  js      short loc_1800B8F0F
0x1800b8e9b  mov     r8b, [rsi+59h]; unsigned __int8
0x1800b8e9f  lea     rdx, aBwritestclear; "bWriteSTClear"
0x1800b8ea6  mov     [rsp+258h+var_230], 0; char
0x1800b8eab  mov     rcx, rdi; unsigned __int16 *
0x1800b8eae  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8eb7  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8ebc  mov     ebx, eax
0x1800b8ebe  test    eax, eax
0x1800b8ec0  js      short loc_1800B8F0F
0x1800b8ec2  mov     r8b, [rsi+5Ah]; unsigned __int8
0x1800b8ec6  lea     rdx, aBwritedefine; "bWriteDefine"
0x1800b8ecd  mov     [rsp+258h+var_230], 0; char
0x1800b8ed2  mov     rcx, rdi; unsigned __int16 *
0x1800b8ed5  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8ede  call    ?TraceUINT8Value@@YAJPEAG0EEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT8Value(ushort *,ushort *,uchar,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8ee3  mov     ebx, eax
0x1800b8ee5  test    eax, eax
0x1800b8ee7  js      short loc_1800B8F0F
0x1800b8ee9  mov     r8d, [rsi+5Ch]; unsigned int
0x1800b8eed  lea     rdx, aDatasize; "dataSize"
0x1800b8ef4  mov     [rsp+258h+var_230], 0; unsigned __int8
0x1800b8ef9  xor     r9d, r9d; unsigned __int8
0x1800b8efc  mov     rcx, rdi; unsigned __int16 *
0x1800b8eff  mov     [rsp+258h+var_238], 0; struct TPM_SYMBOLTABLE_ENTRY *
0x1800b8f08  call    ?TraceUINT32Value@@YAJPEAG0IEPEAUTPM_SYMBOLTABLE_ENTRY@@E@Z; TraceUINT32Value(ushort *,ushort *,uint,uchar,TPM_SYMBOLTABLE_ENTRY *,uchar)
0x1800b8f0d  mov     ebx, eax
0x1800b8f0f  mov     eax, ebx
0x1800b8f11  mov     rcx, [rsp+258h+var_28]
0x1800b8f19  xor     rcx, rsp; StackCookie
0x1800b8f1c  call    __security_check_cookie
0x1800b8f21  mov     rbx, [rsp+258h+arg_10]
0x1800b8f29  add     rsp, 240h
0x1800b8f30  pop     r14
0x1800b8f32  pop     rdi
0x1800b8f33  pop     rsi
0x1800b8f34  retn
```
