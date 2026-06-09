# NetrWkstaUserEnum

- ea: `0x180029e80`
- end: `0x180029f7c`
- name: `NetrWkstaUserEnum`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180009a40`
- `0x18000aed0`
- `0x18000ca10`
- `0x180029e80`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x180029f64`
- `SspiCli!LsaFreeReturnBuffer` at `0x180029f64`

## string_xrefs

- `0x180029ed4`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserEnum(__int64 a1, __int64 a2, int a3, _DWORD *a4, __int64 a5)
{
  bool v5; // cc
  __int64 result; // rax
  __int64 v10; // rcx
  _QWORD *v11; // r9
  _DWORD *v12; // rax
  unsigned int v13; // ebx
  PVOID Buffer; // [rsp+58h] [rbp+10h] BYREF

  v5 = *(_DWORD *)a2 <= 1u;
  Buffer = 0;
  if ( !v5 )
    return 124;
  if ( !*(_QWORD *)(a2 + 8) )
    return 87;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  result = WsLsaEnumUsers(&Buffer);
  if ( !(_DWORD)result )
  {
    if ( Buffer )
    {
      v10 = *(_QWORD *)(a2 + 8);
      v11 = (_QWORD *)(v10 + 8);
      if ( *((_DWORD *)Buffer + 1) )
      {
        v13 = WsEnumUserInfo(*(_DWORD *)a2, a3, (_DWORD)Buffer, (_DWORD)v11, v10, (__int64)a4, a5);
      }
      else
      {
        *v11 = 0;
        v12 = *(_DWORD **)(a2 + 8);
        v13 = 0;
        *v12 = 0;
        *a4 = 0;
      }
      LsaFreeReturnBuffer(Buffer);
      return v13;
    }
    else
    {
      return 31;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029e80  mov     [rsp+arg_0], rbx
0x180029e85  mov     [rsp+arg_10], rsi
0x180029e8a  push    rdi
0x180029e8b  sub     rsp, 40h
0x180029e8f  cmp     dword ptr [rdx], 1
0x180029e92  mov     rdi, r9
0x180029e95  mov     esi, r8d
0x180029e98  mov     [rsp+48h+Buffer], 0
0x180029ea1  mov     rbx, rdx
0x180029ea4  jbe     short loc_180029EB0
0x180029ea6  mov     eax, 7Ch ; '|'
0x180029eab  jmp     loc_180029F6C
0x180029eb0  cmp     qword ptr [rdx+8], 0
0x180029eb5  jnz     short loc_180029EC1
0x180029eb7  mov     eax, 57h ; 'W'
0x180029ebc  jmp     loc_180029F6C
0x180029ec1  mov     rax, cs:ConfigurationInfoSd
0x180029ec8  lea     rcx, WsConfigInfoMapping
0x180029ecf  mov     [rsp+48h+var_18], rcx
0x180029ed4  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180029edb  mov     dword ptr [rsp+48h+var_20], 4
0x180029ee3  mov     [rsp+48h+var_28], rax
0x180029ee8  call    NetpAccessCheckAndAuditEx
0x180029eed  test    eax, eax
0x180029eef  jz      short loc_180029EF8
0x180029ef1  mov     eax, 5
0x180029ef6  jmp     short loc_180029F6C
0x180029ef8  lea     rcx, [rsp+48h+Buffer]; ProtocolReturnBuffer
0x180029efd  call    WsLsaEnumUsers
0x180029f02  test    eax, eax
0x180029f04  jnz     short loc_180029F6C
0x180029f06  mov     r8, [rsp+48h+Buffer]
0x180029f0b  test    r8, r8
0x180029f0e  jnz     short loc_180029F16
0x180029f10  lea     eax, [r8+1Fh]
0x180029f14  jmp     short loc_180029F6C
0x180029f16  cmp     dword ptr [r8+4], 0
0x180029f1b  mov     rcx, [rbx+8]
0x180029f1f  lea     r9, [rcx+8]
0x180029f23  jnz     short loc_180029F40
0x180029f25  mov     qword ptr [r9], 0
0x180029f2c  mov     rax, [rbx+8]
0x180029f30  xor     ebx, ebx
0x180029f32  mov     dword ptr [rax], 0
0x180029f38  mov     dword ptr [rdi], 0
0x180029f3e  jmp     short loc_180029F5F
0x180029f40  mov     rax, [rsp+48h+arg_20]
0x180029f45  mov     edx, esi
0x180029f47  mov     [rsp+48h+var_18], rax
0x180029f4c  mov     [rsp+48h+var_20], rdi
0x180029f51  mov     [rsp+48h+var_28], rcx
0x180029f56  mov     ecx, [rbx]
0x180029f58  call    WsEnumUserInfo
0x180029f5d  mov     ebx, eax
0x180029f5f  mov     rcx, [rsp+48h+Buffer]; Buffer
0x180029f64  call    cs:__imp_LsaFreeReturnBuffer
0x180029f6a  mov     eax, ebx
0x180029f6c  mov     rbx, [rsp+48h+arg_0]
0x180029f71  mov     rsi, [rsp+48h+arg_10]
0x180029f76  add     rsp, 40h
0x180029f7a  pop     rdi
0x180029f7b  retn
```
