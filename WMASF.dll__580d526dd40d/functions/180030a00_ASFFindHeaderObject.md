# ASFFindHeaderObject

- ea: `0x180030a00`
- end: `0x180030c14`
- name: `ASFFindHeaderObject`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010924`
- `0x1800111f8`
- `0x1800122b0`
- `0x180012adc`
- `0x1800156d0`
- `0x180020170`
- `0x1800202a0`
- `0x180020710`
- `0x180022650`
- `0x180022880`
- `0x180022c20`
- `0x180022f80`
- `0x180023270`
- `0x180023590`
- `0x180028160`
- `0x180028510`
- `0x180028f20`
- `0x18002c940`
- `0x18002cc00`
- `0x18002d080`
- `0x18002d7c0`
- `0x18002ffd0`
- `0x1800354f0`
- `0x180039510`
- `0x18003e140`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180030a00`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall ASFFindHeaderObject(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (__fastcall **v8)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  int v10; // ebx
  __int64 (__fastcall **v11)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  struct IWMSCriticalSection *v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h] BYREF

  if ( !a1 || !a4 )
    return 2147942487LL;
  v8 = *a1;
  v15 = 0;
  v14 = 0;
  result = (*v8)(a1, &IID_IASFLibraryPriv, &v14);
  if ( (int)result >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, struct IWMSCriticalSection **))(*(_QWORD *)v14 + 24LL))(v14, &v15);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    if ( v10 >= 0 )
    {
      CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, v15);
      if ( v15 )
      {
        (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v15 + 16LL))(v15);
        v15 = 0;
      }
      v11 = *a1;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v12 = *v11;
      v19 = 0;
      v10 = v12(a1, &IID_IASFUnknownContainer, &v16);
      if ( v10 >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, GUID *, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(
               v16,
               &CLSID_ASFHeaderObject,
               0,
               &v17) >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(v17, &IID_IASFUnknownContainer, &v18);
          if ( v10 >= 0 )
          {
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, a2, 0, &v19) >= 0 )
              v10 = (**(__int64 (__fastcall ***)(__int64, __int64, __int64))v19)(v19, a3, a4);
            else
              v10 = -1072887824;
          }
        }
        else
        {
          v10 = -1072887815;
        }
      }
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v16 = 0;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        v18 = 0;
      }
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v19 = 0;
      }
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x180030a00  push    rbp
0x180030a02  push    rbx
0x180030a03  push    rsi
0x180030a04  push    rdi
0x180030a05  push    r12
0x180030a07  push    r14
0x180030a09  push    r15
0x180030a0b  mov     rbp, rsp
0x180030a0e  sub     rsp, 70h
0x180030a12  mov     rax, cs:__security_cookie
0x180030a19  xor     rax, rsp
0x180030a1c  mov     [rbp+var_8], rax
0x180030a20  xor     r12d, r12d
0x180030a23  mov     rsi, r9
0x180030a26  mov     r14, r8
0x180030a29  mov     r15, rdx
0x180030a2c  mov     rdi, rcx
0x180030a2f  test    rcx, rcx
0x180030a32  jz      loc_180030BF4
0x180030a38  test    r9, r9
0x180030a3b  jz      loc_180030BF4
0x180030a41  mov     rax, [rcx]
0x180030a44  lea     r8, [rbp+var_38]
0x180030a48  lea     rdx, IID_IASFLibraryPriv
0x180030a4f  mov     [rbp+var_30], r12
0x180030a53  mov     [rbp+var_38], r12
0x180030a57  mov     rax, [rax]
0x180030a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a5f  test    eax, eax
0x180030a61  js      loc_180030BF9
0x180030a67  mov     rcx, [rbp+var_38]
0x180030a6b  lea     rdx, [rbp+var_30]
0x180030a6f  mov     rax, [rcx]
0x180030a72  mov     rax, [rax+18h]
0x180030a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a7b  mov     rdx, [rbp+var_38]
0x180030a7f  mov     ebx, eax
0x180030a81  test    rdx, rdx
0x180030a84  jz      short loc_180030A99
0x180030a86  mov     rcx, [rdx]
0x180030a89  mov     rax, [rcx+10h]
0x180030a8d  mov     rcx, rdx
0x180030a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a95  mov     [rbp+var_38], r12
0x180030a99  test    ebx, ebx
0x180030a9b  jns     short loc_180030AA4
0x180030a9d  mov     eax, ebx
0x180030a9f  jmp     loc_180030BF9
0x180030aa4  mov     rdx, [rbp+var_30]; struct IWMSCriticalSection *
0x180030aa8  lea     rcx, [rbp+var_40]; this
0x180030aac  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180030ab1  mov     rcx, [rbp+var_30]
0x180030ab5  test    rcx, rcx
0x180030ab8  jz      short loc_180030ACA
0x180030aba  mov     rax, [rcx]
0x180030abd  mov     rax, [rax+10h]
0x180030ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ac6  mov     [rbp+var_30], r12
0x180030aca  mov     rax, [rdi]
0x180030acd  lea     r8, [rbp+var_28]
0x180030ad1  lea     rdx, IID_IASFUnknownContainer
0x180030ad8  mov     [rbp+var_28], r12
0x180030adc  mov     rcx, rdi
0x180030adf  mov     [rbp+var_20], r12
0x180030ae3  mov     [rbp+var_18], r12
0x180030ae7  mov     rax, [rax]
0x180030aea  mov     [rbp+var_10], r12
0x180030aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030af3  mov     ebx, eax
0x180030af5  test    eax, eax
0x180030af7  js      loc_180030B82
0x180030afd  mov     rcx, [rbp+var_28]
0x180030b01  lea     r9, [rbp+var_20]
0x180030b05  xor     r8d, r8d
0x180030b08  lea     rdx, CLSID_ASFHeaderObject
0x180030b0f  mov     rax, [rcx]
0x180030b12  mov     rax, [rax+20h]
0x180030b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b1b  test    eax, eax
0x180030b1d  jns     short loc_180030B26
0x180030b1f  mov     ebx, 0C00D07F9h
0x180030b24  jmp     short loc_180030B82
0x180030b26  mov     rcx, [rbp+var_20]
0x180030b2a  lea     r8, [rbp+var_18]
0x180030b2e  lea     rdx, IID_IASFUnknownContainer
0x180030b35  mov     rax, [rcx]
0x180030b38  mov     rax, [rax]
0x180030b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b40  mov     ebx, eax
0x180030b42  test    eax, eax
0x180030b44  js      short loc_180030B82
0x180030b46  mov     rcx, [rbp+var_18]
0x180030b4a  lea     r9, [rbp+var_10]
0x180030b4e  xor     r8d, r8d
0x180030b51  mov     rdx, r15
0x180030b54  mov     rax, [rcx]
0x180030b57  mov     rax, [rax+20h]
0x180030b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b60  test    eax, eax
0x180030b62  jns     short loc_180030B6B
0x180030b64  mov     ebx, 0C00D07F0h
0x180030b69  jmp     short loc_180030B82
0x180030b6b  mov     rcx, [rbp+var_10]
0x180030b6f  mov     r8, rsi
0x180030b72  mov     rdx, r14
0x180030b75  mov     rax, [rcx]
0x180030b78  mov     rax, [rax]
0x180030b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b80  mov     ebx, eax
0x180030b82  mov     rcx, [rbp+var_28]
0x180030b86  test    rcx, rcx
0x180030b89  jz      short loc_180030B9B
0x180030b8b  mov     rax, [rcx]
0x180030b8e  mov     rax, [rax+10h]
0x180030b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b97  mov     [rbp+var_28], r12
0x180030b9b  mov     rcx, [rbp+var_20]
0x180030b9f  test    rcx, rcx
0x180030ba2  jz      short loc_180030BB4
0x180030ba4  mov     rax, [rcx]
0x180030ba7  mov     rax, [rax+10h]
0x180030bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bb0  mov     [rbp+var_20], r12
0x180030bb4  mov     rcx, [rbp+var_18]
0x180030bb8  test    rcx, rcx
0x180030bbb  jz      short loc_180030BCD
0x180030bbd  mov     rax, [rcx]
0x180030bc0  mov     rax, [rax+10h]
0x180030bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bc9  mov     [rbp+var_18], r12
0x180030bcd  mov     rcx, [rbp+var_10]
0x180030bd1  test    rcx, rcx
0x180030bd4  jz      short loc_180030BE6
0x180030bd6  mov     rax, [rcx]
0x180030bd9  mov     rax, [rax+10h]
0x180030bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030be2  mov     [rbp+var_10], r12
0x180030be6  lea     rcx, [rbp+var_40]; this
0x180030bea  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180030bef  jmp     loc_180030A9D
0x180030bf4  mov     eax, 80070057h
0x180030bf9  mov     rcx, [rbp+var_8]
0x180030bfd  xor     rcx, rsp; StackCookie
0x180030c00  call    __security_check_cookie
0x180030c05  add     rsp, 70h
0x180030c09  pop     r15
0x180030c0b  pop     r14
0x180030c0d  pop     r12
0x180030c0f  pop     rdi
0x180030c10  pop     rsi
0x180030c11  pop     rbx
0x180030c12  pop     rbp
0x180030c13  retn
```
