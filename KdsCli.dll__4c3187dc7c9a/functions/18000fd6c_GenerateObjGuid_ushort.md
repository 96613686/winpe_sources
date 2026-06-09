# GenerateObjGuid(ushort * *)

- ea: `0x18000fd6c`
- end: `0x18000fe24`
- name: `?GenerateObjGuid@@YAJPEAPEAG@Z`
- size: `184`
- prototype: `__int64 __fastcall(RPC_WSTR *StringUuid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180001630`
- `0x18000fd6c`
- `0x18001a450`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18000fda1`
- `bcrypt!BCryptGenRandom` at `0x18000fda1`
- `RPCRT4!UuidToStringW` at `0x18000fdd4`
- `RPCRT4!UuidToStringW` at `0x18000fdd4`

## string_xrefs

- `0x18000fdb3`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x18000fde6`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall GenerateObjGuid(RPC_WSTR *StringUuid)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  RPC_STATUS v4; // eax
  int v5; // edi
  UCHAR pbBuffer[16]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)pbBuffer = 0;
  v2 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = 0;
    v4 = UuidToStringW((const UUID *)pbBuffer, StringUuid);
    v5 = v4;
    if ( v4 )
    {
      SidKeyDebugTraceError(v4, "rpcStatus", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x70u);
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
      else
        return (unsigned int)v5;
    }
  }
  else
  {
    SidKeyDebugTraceError(v2, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x67u);
  }
  return v3;
}

```

## disassembly

```asm
0x18000fd6c  mov     [rsp+arg_8], rbx
0x18000fd71  push    rdi
0x18000fd72  sub     rsp, 40h
0x18000fd76  mov     rax, cs:__security_cookie
0x18000fd7d  xor     rax, rsp
0x18000fd80  mov     [rsp+48h+var_18], rax
0x18000fd85  mov     r9d, 2; dwFlags
0x18000fd8b  lea     rdx, [rsp+48h+pbBuffer]; pbBuffer
0x18000fd90  mov     rdi, rcx
0x18000fd93  xorps   xmm0, xmm0
0x18000fd96  xor     ecx, ecx; hAlgorithm
0x18000fd98  movups  xmmword ptr [rsp+48h+pbBuffer], xmm0
0x18000fd9d  lea     r8d, [r9+0Eh]; cbBuffer
0x18000fda1  call    cs:__imp_BCryptGenRandom
0x18000fda7  mov     ebx, eax
0x18000fda9  test    eax, eax
0x18000fdab  jns     short loc_18000FDCA
0x18000fdad  mov     r9d, 67h ; 'g'; unsigned int
0x18000fdb3  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fdba  lea     rdx, aHr; "hr"
0x18000fdc1  mov     ecx, eax; unsigned int
0x18000fdc3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fdc8  jmp     short loc_18000FE0A
0x18000fdca  mov     rdx, rdi; StringUuid
0x18000fdcd  lea     rcx, [rsp+48h+pbBuffer]; Uuid
0x18000fdd2  xor     ebx, ebx
0x18000fdd4  call    cs:__imp_UuidToStringW
0x18000fdda  mov     edi, eax
0x18000fddc  test    eax, eax
0x18000fdde  jz      short loc_18000FE0A
0x18000fde0  lea     r9d, [rbx+70h]; unsigned int
0x18000fde4  mov     ecx, eax; unsigned int
0x18000fde6  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fded  lea     rdx, aRpcstatus; "rpcStatus"
0x18000fdf4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fdf9  test    edi, edi
0x18000fdfb  jg      short loc_18000FE01
0x18000fdfd  mov     ebx, edi
0x18000fdff  jmp     short loc_18000FE0A
0x18000fe01  movzx   ebx, di
0x18000fe04  or      ebx, 80070000h
0x18000fe0a  mov     eax, ebx
0x18000fe0c  mov     rcx, [rsp+48h+var_18]
0x18000fe11  xor     rcx, rsp; StackCookie
0x18000fe14  call    __security_check_cookie
0x18000fe19  mov     rbx, [rsp+48h+arg_8]
0x18000fe1e  add     rsp, 40h
0x18000fe22  pop     rdi
0x18000fe23  retn
```
