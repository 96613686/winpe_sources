# DpspDispatchInstanceList

- ea: `0x180002dc0`
- end: `0x180002efb`
- name: `DpspDispatchInstanceList`
- size: `315`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003498`
- `0x1800035d0`
- `0x180004864`
- `0x180004b18`
- `0x180004c18`
- `0x180004de4`
- `0x18000c6bc`
- `0x180011fd4`

## callees

- `0x180001ff0`
- `0x180002dc0`
- `0x180009090`

## pseudocode

```c
void __fastcall DpspDispatchInstanceList(struct __SESSIONINFO ***a1, __int64 a2, __int64 a3)
{
  struct __SESSIONINFO **v6; // rbx
  struct __SESSIONINFO ***v7; // rdi
  struct __SESSIONINFO ***v8; // rax
  struct __SESSIONINFO ***v9; // rax
  int v10; // eax
  struct __SESSIONINFO ***v11; // rcx
  __int64 Args; // [rsp+20h] [rbp-18h]

  if ( a1 )
  {
    v6 = *a1;
    if ( *a1 != (struct __SESSIONINFO **)a1 )
    {
      do
      {
        v7 = (struct __SESSIONINFO ***)*v6;
        if ( *((struct __SESSIONINFO ***)*v6 + 1) != v6 || (v8 = (struct __SESSIONINFO ***)v6[1], *v8 != v6) )
LABEL_14:
          __fastfail(3u);
        *v8 = (struct __SESSIONINFO **)v7;
        v7[1] = (struct __SESSIONINFO **)v8;
        if ( ((_DWORD)v6[13] & 0x200) != 0 )
        {
          v9 = *(struct __SESSIONINFO ****)(a3 + 8);
          if ( *v9 != (struct __SESSIONINFO **)a3 )
            goto LABEL_14;
          *v6 = (struct __SESSIONINFO *)a3;
          v6[1] = (struct __SESSIONINFO *)v9;
          *v9 = v6;
          *(_QWORD *)(a3 + 8) = v6;
        }
        else
        {
          v10 = DpspAttemptScenarioCompletion(v6);
          if ( v10 < 0 )
          {
            *((_DWORD *)v6 + 33) = v10;
            v11 = *(struct __SESSIONINFO ****)(a2 + 8);
            if ( *v11 != (struct __SESSIONINFO **)a2 )
              goto LABEL_14;
            *v6 = (struct __SESSIONINFO *)a2;
            v6[1] = (struct __SESSIONINFO *)v11;
            *v11 = v6;
            *(_QWORD *)(a2 + 8) = v6;
            LODWORD(Args) = (unsigned __int16)v10;
            WdipTraceError(
              (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
              (__int64)L"DpspDispatchInstanceList",
              1471,
              (const wchar_t *)L"Error = %d",
              Args);
          }
        }
        v6 = (struct __SESSIONINFO **)v7;
      }
      while ( v7 != a1 );
    }
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (__int64)L"DpspDispatchInstanceList",
      1445,
      (const wchar_t *)L"Error = %d",
      87);
  }
}

```

## disassembly

```asm
0x180002dc0  mov     [rsp+arg_10], rbp
0x180002dc5  mov     [rsp+arg_18], rsi
0x180002dca  push    r14
0x180002dcc  sub     rsp, 30h
0x180002dd0  mov     rsi, r8
0x180002dd3  mov     rbp, rdx
0x180002dd6  mov     r14, rcx
0x180002dd9  test    rcx, rcx
0x180002ddc  jnz     short loc_180002E17
0x180002dde  lea     r9, aErrorD; "Error = %d"
0x180002de5  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180002ded  mov     r8d, 5A5h; int
0x180002df3  lea     rdx, aDpspdispatchin; "DpspDispatchInstanceList"
0x180002dfa  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002e01  call    WdipTraceError
0x180002e06  mov     rbp, [rsp+38h+arg_10]
0x180002e0b  mov     rsi, [rsp+38h+arg_18]
0x180002e10  add     rsp, 30h
0x180002e14  pop     r14
0x180002e16  retn
0x180002e17  mov     [rsp+38h+arg_0], rbx
0x180002e1c  mov     rbx, [rcx]
0x180002e1f  cmp     rbx, r14
0x180002e22  jz      loc_180002EDE
0x180002e28  mov     [rsp+38h+arg_8], rdi
0x180002e2d  nop     dword ptr [rax]
0x180002e30  mov     rdi, [rbx]
0x180002e33  cmp     [rdi+8], rbx
0x180002e37  jnz     loc_180002EF4
0x180002e3d  mov     rax, [rbx+8]
0x180002e41  cmp     [rax], rbx
0x180002e44  jnz     loc_180002EF4
0x180002e4a  mov     [rax], rdi
0x180002e4d  mov     [rdi+8], rax
0x180002e51  mov     eax, [rbx+68h]
0x180002e54  bt      eax, 9
0x180002e58  jnb     short loc_180002E77
0x180002e5a  mov     rax, [rsi+8]
0x180002e5e  cmp     [rax], rsi
0x180002e61  jnz     loc_180002EF4
0x180002e67  mov     [rbx], rsi
0x180002e6a  mov     [rbx+8], rax
0x180002e6e  mov     [rax], rbx
0x180002e71  mov     [rsi+8], rbx
0x180002e75  jmp     short loc_180002ECD
0x180002e77  mov     edx, [rbx+0CCh]
0x180002e7d  mov     rcx, rbx; struct INSTANCEINFO *
0x180002e80  call    DpspAttemptScenarioCompletion
0x180002e85  test    eax, eax
0x180002e87  jns     short loc_180002ECD
0x180002e89  mov     [rbx+84h], eax
0x180002e8f  mov     rcx, [rbp+8]
0x180002e93  cmp     [rcx], rbp
0x180002e96  jnz     short loc_180002EF4
0x180002e98  mov     [rbx], rbp
0x180002e9b  mov     [rbx+8], rcx
0x180002e9f  mov     [rcx], rbx
0x180002ea2  mov     [rbp+8], rbx
0x180002ea6  movzx   eax, ax
0x180002ea9  lea     r9, aErrorD; "Error = %d"
0x180002eb0  mov     r8d, 5BFh; int
0x180002eb6  mov     dword ptr [rsp+38h+Args], eax; Args
0x180002eba  lea     rdx, aDpspdispatchin; "DpspDispatchInstanceList"
0x180002ec1  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002ec8  call    WdipTraceError
0x180002ecd  mov     rbx, rdi
0x180002ed0  cmp     rdi, r14
0x180002ed3  jnz     loc_180002E30
0x180002ed9  mov     rdi, [rsp+38h+arg_8]
0x180002ede  mov     rbx, [rsp+38h+arg_0]
0x180002ee3  mov     rbp, [rsp+38h+arg_10]
0x180002ee8  mov     rsi, [rsp+38h+arg_18]
0x180002eed  add     rsp, 30h
0x180002ef1  pop     r14
0x180002ef3  retn
0x180002ef4  mov     ecx, 3
0x180002ef9  int     29h; Win8: RtlFailFast(ecx)
```
