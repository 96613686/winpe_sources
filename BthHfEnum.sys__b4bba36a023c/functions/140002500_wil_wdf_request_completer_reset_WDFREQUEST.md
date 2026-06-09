# wil::wdf_request_completer::reset(WDFREQUEST__ *)

- ea: `0x140002500`
- end: `0x1400025c9`
- name: `?reset@wdf_request_completer@wil@@QEAAXPEAUWDFREQUEST__@@@Z`
- size: `201`
- prototype: `void __fastcall(wil::wdf_request_completer *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003330`

## callees

- `0x140002500`
- `0x14001ae00`

## pseudocode

```c
void __fastcall wil::wdf_request_completer::reset(
        wil::wdf_request_completer *this,
        struct WDFREQUEST__ *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdx
  char v7; // al
  char v8; // cl
  __int64 v9; // r8

  v6 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    v7 = *((_BYTE *)this + 21);
    v8 = v7 & 1;
    if ( (v7 & 2) != 0 )
    {
      if ( v8 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2200))(
          WdfDriverGlobals,
          v6,
          *((_QWORD *)this + 1));
      LOBYTE(a4) = *((_BYTE *)this + 20);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64))(WdfFunctions_01015 + 2112))(
        WdfDriverGlobals,
        *(_QWORD *)this,
        *((unsigned int *)this + 4),
        a4);
    }
    else
    {
      v9 = *((unsigned int *)this + 4);
      if ( v8 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD))(WdfFunctions_01015 + 2120))(
          WdfDriverGlobals,
          v6,
          v9,
          *((_QWORD *)this + 1));
      else
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
          WdfDriverGlobals,
          v6,
          v9);
    }
  }
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 4) = -1073741823;
  *((_QWORD *)this + 1) = 0;
  *((_WORD *)this + 10) = 0;
}

```

## disassembly

```asm
0x140002500  mov     [rsp+arg_0], rbx
0x140002505  push    rdi
0x140002506  sub     rsp, 30h
0x14000250a  mov     rdi, rdx
0x14000250d  mov     rbx, rcx
0x140002510  mov     rdx, [rcx]
0x140002513  test    rdx, rdx
0x140002516  jz      loc_1400025A5
0x14000251c  mov     al, [rcx+15h]
0x14000251f  mov     cl, al
0x140002521  and     cl, 1
0x140002524  test    al, 2
0x140002526  jz      short loc_140002571
0x140002528  test    cl, cl
0x14000252a  jz      short loc_14000254A
0x14000252c  mov     rax, cs:WdfFunctions_01015
0x140002533  mov     r8, [rbx+8]
0x140002537  mov     rcx, cs:WdfDriverGlobals
0x14000253e  mov     rax, [rax+898h]
0x140002545  call    _guard_dispatch_icall
0x14000254a  mov     rax, cs:WdfFunctions_01015
0x140002551  mov     r9b, [rbx+14h]
0x140002555  mov     r8d, [rbx+10h]
0x140002559  mov     rdx, [rbx]
0x14000255c  mov     rax, [rax+840h]
0x140002563  mov     rcx, cs:WdfDriverGlobals
0x14000256a  call    _guard_dispatch_icall
0x14000256f  jmp     short loc_1400025A5
0x140002571  mov     rax, cs:WdfFunctions_01015
0x140002578  test    cl, cl
0x14000257a  mov     rcx, cs:WdfDriverGlobals
0x140002581  mov     r8d, [rbx+10h]
0x140002585  jz      short loc_140002599
0x140002587  mov     rax, [rax+848h]
0x14000258e  mov     r9, [rbx+8]
0x140002592  call    _guard_dispatch_icall
0x140002597  jmp     short loc_1400025A5
0x140002599  mov     rax, [rax+838h]
0x1400025a0  call    _guard_dispatch_icall
0x1400025a5  mov     [rbx], rdi
0x1400025a8  mov     dword ptr [rbx+10h], 0C0000001h
0x1400025af  mov     qword ptr [rbx+8], 0
0x1400025b7  mov     word ptr [rbx+14h], 0
0x1400025bd  mov     rbx, [rsp+38h+arg_0]
0x1400025c2  add     rsp, 30h
0x1400025c6  pop     rdi
0x1400025c7  retn
```
