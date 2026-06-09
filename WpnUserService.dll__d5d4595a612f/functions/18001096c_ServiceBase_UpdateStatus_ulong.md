# ServiceBase::_UpdateStatus(ulong)

- ea: `0x18001096c`
- end: `0x180010a57`
- name: `?_UpdateStatus@ServiceBase@@AEAAJK@Z`
- size: `235`
- prototype: `__int64 __fastcall(ServiceBase *this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000edbc`
- `0x1800102c0`
- `0x180010444`

## callees

- `0x180006224`
- `0x180006244`
- `0x18001096c`
- `0x180012010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800109d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800109d4`

## string_xrefs

- `0x180010985`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x1800109e3`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_UpdateStatus(ServiceBase *this, int a2)
{
  const char *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 9) )
  {
    *((_DWORD *)this + 25) = a2;
    if ( a2 == 1 || a2 == 4 )
    {
      *((_DWORD *)this + 29) = 0;
      if ( a2 == 1 )
      {
        if ( (*(unsigned int (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 72LL))(this) )
        {
          v5 = *(_QWORD *)this;
          *((_DWORD *)this + 27) = 1066;
          *((_DWORD *)this + 28) = (*(__int64 (__fastcall **)(ServiceBase *))(v5 + 72))(this);
        }
      }
      else
      {
        v6 = *(_QWORD *)this;
        *((_DWORD *)this + 26) |= 0x401u;
        *((_DWORD *)this + 26) |= (*(__int64 (**)(void))(v6 + 56))();
      }
    }
    else
    {
      ++*((_DWORD *)this + 29);
      if ( (unsigned int)(a2 - 2) <= 1 )
        *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
    }
    if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 9), (LPSERVICE_STATUS)((char *)this + 96)) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x160,
               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
               v4);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)0x80070006LL,
      v7);
    return 2147942406LL;
  }
}

```

## disassembly

```asm
0x18001096c  mov     [rsp+arg_0], rbx
0x180010971  push    rdi; int
0x180010972  sub     rsp, 20h
0x180010976  cmp     qword ptr [rcx+48h], 0
0x18001097b  mov     rbx, rcx
0x18001097e  jnz     short loc_1800109A5
0x180010980  mov     rcx, [rsp+28h]; this
0x180010985  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001098c  mov     ebx, 80070006h
0x180010991  mov     edx, 136h; void *
0x180010996  mov     r9d, ebx; char *
0x180010999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001099e  mov     eax, ebx
0x1800109a0  jmp     loc_180010A4C
0x1800109a5  mov     [rcx+64h], edx
0x1800109a8  cmp     edx, 1
0x1800109ab  jz      short loc_1800109F6
0x1800109ad  cmp     edx, 4
0x1800109b0  jz      short loc_1800109F6
0x1800109b2  inc     dword ptr [rcx+74h]
0x1800109b5  lea     eax, [rdx-2]
0x1800109b8  cmp     eax, 1
0x1800109bb  ja      short loc_1800109CC
0x1800109bd  mov     rax, [rcx]
0x1800109c0  mov     rax, [rax+40h]
0x1800109c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c9  mov     [rbx+78h], eax
0x1800109cc  mov     rcx, [rbx+48h]; hServiceStatus
0x1800109d0  lea     rdx, [rbx+60h]; lpServiceStatus
0x1800109d4  call    cs:__imp_SetServiceStatus
0x1800109da  test    eax, eax
0x1800109dc  jnz     short loc_180010A4A
0x1800109de  mov     rcx, [rsp+28h]; this
0x1800109e3  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800109ea  mov     edx, 160h; void *
0x1800109ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800109f4  jmp     short loc_180010A4C
0x1800109f6  mov     dword ptr [rcx+74h], 0
0x1800109fd  cmp     edx, 1
0x180010a00  jnz     short loc_180010A2D
0x180010a02  mov     rax, [rcx]
0x180010a05  mov     rax, [rax+48h]
0x180010a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a0e  test    eax, eax
0x180010a10  jz      short loc_1800109CC
0x180010a12  mov     rax, [rbx]
0x180010a15  mov     rcx, rbx
0x180010a18  mov     dword ptr [rbx+6Ch], 42Ah
0x180010a1f  mov     rax, [rax+48h]
0x180010a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a28  mov     [rbx+70h], eax
0x180010a2b  jmp     short loc_1800109CC
0x180010a2d  cmp     edx, 4
0x180010a30  jnz     short loc_1800109B5
0x180010a32  mov     rax, [rcx]
0x180010a35  or      dword ptr [rcx+68h], 401h
0x180010a3c  mov     rax, [rax+38h]
0x180010a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a45  or      [rbx+68h], eax
0x180010a48  jmp     short loc_1800109CC
0x180010a4a  xor     eax, eax
0x180010a4c  mov     rbx, [rsp+28h+arg_0]
0x180010a51  add     rsp, 20h
0x180010a55  pop     rdi
0x180010a56  retn
```
