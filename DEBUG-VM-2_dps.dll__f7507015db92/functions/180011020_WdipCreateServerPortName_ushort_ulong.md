# WdipCreateServerPortName(ushort *,ulong)

- ea: `0x180011020`
- end: `0x180011165`
- name: `?WdipCreateServerPortName@@YAJPEAGK@Z`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011274`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x18000f3d0`
- `0x180011020`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001106f`
- `RPCRT4!UuidCreate` at `0x18001106f`
- `RPCRT4!RpcStringFreeW` at `0x180011145`
- `RPCRT4!RpcStringFreeW` at `0x180011145`
- `RPCRT4!UuidToStringW` at `0x1800110a4`
- `RPCRT4!UuidToStringW` at `0x1800110a4`

## string_xrefs

- `0x180011125`: `WdipCreateServerPortName`

## pseudocode

```c
__int64 __fastcall WdipCreateServerPortName(unsigned __int16 *a1)
{
  signed int Args; // ebx
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  int v5; // eax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  if ( a1 )
  {
    v3 = UuidCreate(&Uuid);
    Args = v3;
    if ( v3 > 0 )
      Args = (unsigned __int16)v3 | 0x80070000;
    if ( Args >= 0 )
    {
      v4 = UuidToStringW(&Uuid, &StringUuid);
      Args = v4;
      if ( v4 > 0 )
        Args = (unsigned __int16)v4 | 0x80070000;
      if ( Args >= 0 )
      {
        if ( StringUuid )
        {
          v5 = StringCchPrintfW(a1, 0x80u, L"%sWDI_{%s}", L"\\BaseNamedObjects\\", StringUuid);
          Args = v5;
          if ( v5 < 0 )
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
              (int)L"WdipCreateServerPortName",
              1321,
              (int)L"Error = %d",
              v5);
        }
        else
        {
          Args = -2147024882;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
            (int)L"WdipCreateServerPortName",
            1313,
            (int)L"Error = %d",
            14);
        }
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
          (int)L"WdipCreateServerPortName",
          1312,
          (int)L"Error = %d",
          Args);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
        (int)L"WdipCreateServerPortName",
        1307,
        (int)L"Error = %d",
        Args);
    }
  }
  else
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"WdipCreateServerPortName",
      1299,
      (int)L"Error = %d",
      87);
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180011020  mov     [rsp+arg_8], rbx
0x180011025  push    rdi
0x180011026  sub     rsp, 50h
0x18001102a  mov     rax, cs:__security_cookie
0x180011031  xor     rax, rsp
0x180011034  mov     [rsp+58h+var_10], rax
0x180011039  mov     [rsp+58h+StringUuid], 0
0x180011042  xorps   xmm0, xmm0
0x180011045  mov     rdi, rcx
0x180011048  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x18001104d  test    rcx, rcx
0x180011050  jnz     short loc_18001106A
0x180011052  mov     ebx, 80070057h
0x180011057  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18001105f  mov     r8d, 513h
0x180011065  jmp     loc_18001111E
0x18001106a  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18001106f  call    cs:__imp_UuidCreate
0x180011075  mov     ebx, eax
0x180011077  test    eax, eax
0x180011079  jle     short loc_180011084
0x18001107b  movzx   ebx, ax
0x18001107e  or      ebx, 80070000h
0x180011084  test    ebx, ebx
0x180011086  jns     short loc_18001109A
0x180011088  movzx   eax, bx
0x18001108b  mov     r8d, 51Bh
0x180011091  mov     dword ptr [rsp+58h+Args], eax
0x180011095  jmp     loc_18001111E
0x18001109a  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x18001109f  lea     rcx, [rsp+58h+Uuid]; Uuid
0x1800110a4  call    cs:__imp_UuidToStringW
0x1800110aa  mov     ebx, eax
0x1800110ac  test    eax, eax
0x1800110ae  jle     short loc_1800110B9
0x1800110b0  movzx   ebx, ax
0x1800110b3  or      ebx, 80070000h
0x1800110b9  test    ebx, ebx
0x1800110bb  jns     short loc_1800110CC
0x1800110bd  movzx   eax, bx
0x1800110c0  mov     r8d, 520h
0x1800110c6  mov     dword ptr [rsp+58h+Args], eax
0x1800110ca  jmp     short loc_18001111E
0x1800110cc  mov     rax, [rsp+58h+StringUuid]
0x1800110d1  test    rax, rax
0x1800110d4  jnz     short loc_1800110EB
0x1800110d6  mov     ebx, 8007000Eh
0x1800110db  mov     dword ptr [rsp+58h+Args], 0Eh
0x1800110e3  mov     r8d, 521h
0x1800110e9  jmp     short loc_18001111E
0x1800110eb  lea     r9, aBasenamedobjec; "\\BaseNamedObjects\\"
0x1800110f2  mov     qword ptr [rsp+58h+Args], rax
0x1800110f7  lea     r8, aSwdiS; "%sWDI_{%s}"
0x1800110fe  mov     edx, 80h; unsigned __int64
0x180011103  mov     rcx, rdi; unsigned __int16 *
0x180011106  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001110b  mov     ebx, eax
0x18001110d  test    eax, eax
0x18001110f  jns     short loc_180011138
0x180011111  movzx   ecx, ax
0x180011114  mov     r8d, 529h; int
0x18001111a  mov     dword ptr [rsp+58h+Args], ecx; Args
0x18001111e  lea     r9, aErrorD; "Error = %d"
0x180011125  lea     rdx, aWdipcreateserv; "WdipCreateServerPortName"
0x18001112c  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180011133  call    WdipTraceError
0x180011138  cmp     [rsp+58h+StringUuid], 0
0x18001113e  jz      short loc_18001114B
0x180011140  lea     rcx, [rsp+58h+StringUuid]; String
0x180011145  call    cs:__imp_RpcStringFreeW
0x18001114b  mov     eax, ebx
0x18001114d  mov     rcx, [rsp+58h+var_10]
0x180011152  xor     rcx, rsp; StackCookie
0x180011155  call    __security_check_cookie
0x18001115a  mov     rbx, [rsp+58h+arg_8]
0x18001115f  add     rsp, 50h
0x180011163  pop     rdi
0x180011164  retn
```
