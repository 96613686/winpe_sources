# PimIMService::HandleTranslatedChange(PO_CHANGETYPE,TransactionData *,USOID &)

- ea: `0x1800081a0`
- end: `0x1800082bc`
- name: `?HandleTranslatedChange@PimIMService@@UEAAJW4PO_CHANGETYPE@@PEAUTransactionData@@AEAUUSOID@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x1800081a0`
- `0x1800086a0`
- `0x18000d63c`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x1800081e7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180008216`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000822f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::HandleTranslatedChange(__int64 a1, __int64 a2, _DWORD *a3, __int64 *a4)
{
  int v5; // eax
  int v6; // ebx
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebp
  int v12; // ebx
  int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // ebx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+38h] [rbp-30h]

  v5 = *((_DWORD *)a4 + 2);
  v6 = a2;
  v17 = *a4;
  v18 = v5;
  v8 = FailOnServiceShutdown(a1, a2, (__int64)a3);
  v10 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2390);
    return v10;
  }
  v12 = v6 - 1;
  if ( !v12 || (v13 = v12 - 1) == 0 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)a1 + 144LL))(a1, &v17, 0);
    if ( v16 >= 0 )
    {
      ++*a3;
      return (unsigned int)v16;
    }
    v14 = 2397;
LABEL_12:
    v15 = 1;
    goto LABEL_7;
  }
  if ( v13 == 2 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 152LL))(a1, &v17);
    if ( v16 == -2147023728 )
      return 0;
    ++*a3;
    if ( v16 >= 0 )
      return (unsigned int)v16;
    v14 = 2415;
    goto LABEL_12;
  }
  Log_AssertionEvent(
    v9,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    2424);
  v14 = 2425;
  v15 = 0;
  v16 = -2147467259;
LABEL_7:
  Log_HREvent(
    (unsigned int)v16,
    v15,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800081a0  mov     [rsp+arg_8], rbx
0x1800081a5  push    rbp
0x1800081a6  push    rsi
0x1800081a7  push    rdi
0x1800081a8  sub     rsp, 50h
0x1800081ac  mov     rax, cs:__security_cookie
0x1800081b3  xor     rax, rsp
0x1800081b6  mov     [rsp+68h+var_28], rax
0x1800081bb  movsd   xmm0, qword ptr [r9]
0x1800081c0  mov     rdi, r8
0x1800081c3  mov     eax, [r9+8]
0x1800081c7  mov     ebx, edx
0x1800081c9  movsd   [rsp+68h+var_38], xmm0
0x1800081cf  mov     rsi, rcx
0x1800081d2  mov     [rsp+68h+var_30], eax
0x1800081d6  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x1800081db  mov     ebp, eax
0x1800081dd  test    eax, eax
0x1800081df  jns     short loc_180008201
0x1800081e1  mov     r9d, 956h
0x1800081e7  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800081ee  mov     edx, 1
0x1800081f3  mov     ecx, eax
0x1800081f5  call    Log_HREvent
0x1800081fa  mov     eax, ebp
0x1800081fc  jmp     loc_1800082A2
0x180008201  sub     ebx, 1
0x180008204  jz      short loc_180008276
0x180008206  sub     ebx, 1
0x180008209  jz      short loc_180008276
0x18000820b  cmp     ebx, 2
0x18000820e  jz      short loc_18000823F
0x180008210  mov     r8d, 978h
0x180008216  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000821d  call    Log_AssertionEvent
0x180008222  mov     r9d, 979h
0x180008228  xor     edx, edx
0x18000822a  mov     ebx, 80004005h
0x18000822f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008236  mov     ecx, ebx
0x180008238  call    Log_HREvent
0x18000823d  jmp     short loc_1800082A0
0x18000823f  mov     rax, [rsi]
0x180008242  lea     rdx, [rsp+68h+var_38]
0x180008247  mov     rcx, rsi
0x18000824a  mov     rax, [rax+98h]
0x180008251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008256  mov     ebx, eax
0x180008258  cmp     eax, 80070490h
0x18000825d  jnz     short loc_180008263
0x18000825f  xor     ebx, ebx
0x180008261  jmp     short loc_1800082A0
0x180008263  inc     dword ptr [rdi]
0x180008265  test    ebx, ebx
0x180008267  jns     short loc_1800082A0
0x180008269  mov     r9d, 96Fh
0x18000826f  mov     edx, 1
0x180008274  jmp     short loc_18000822F
0x180008276  mov     rax, [rsi]
0x180008279  lea     rdx, [rsp+68h+var_38]
0x18000827e  xor     r8d, r8d
0x180008281  mov     rcx, rsi
0x180008284  mov     rax, [rax+90h]
0x18000828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008290  mov     ebx, eax
0x180008292  test    eax, eax
0x180008294  jns     short loc_18000829E
0x180008296  mov     r9d, 95Dh
0x18000829c  jmp     short loc_18000826F
0x18000829e  inc     dword ptr [rdi]
0x1800082a0  mov     eax, ebx
0x1800082a2  mov     rcx, [rsp+68h+var_28]
0x1800082a7  xor     rcx, rsp; StackCookie
0x1800082aa  call    __security_check_cookie
0x1800082af  mov     rbx, [rsp+68h+arg_8]
0x1800082b4  add     rsp, 50h
0x1800082b8  pop     rdi
0x1800082b9  pop     rsi
0x1800082ba  pop     rbp
0x1800082bb  retn
```
