# SocketBrokerContext::DeletePushEnableContext(void)

- ea: `0x18002666c`
- end: `0x18002671e`
- name: `?DeletePushEnableContext@SocketBrokerContext@@AEAAKXZ`
- size: `178`
- prototype: `__int64 __fastcall(SocketBrokerContext *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018d40`
- `0x180019470`
- `0x180026164`
- `0x180026490`

## callees

- `0x18000a0a0`
- `0x18001d8e0`
- `0x18002666c`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x1800266d6`
- `NSI!NsiSetAllParameters` at `0x1800266d6`

## string_xrefs

- `0x1800266ee`: `DeletePushEnableContext: Failed to clear wpm context`

## pseudocode

```c
__int64 __fastcall SocketBrokerContext::DeletePushEnableContext(SocketBrokerContext *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _DWORD v8[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-20h]

  v1 = *((_DWORD *)this + 32);
  v2 = 0;
  v8[1] = 0;
  if ( v1 )
  {
    v8[0] = v1;
    v9 = *((_QWORD *)this + 17);
    v4 = NsiSetAllParameters(1, 3, NPI_MS_TCP_MODULEID, 31, v8, 16, 0, 0);
    v2 = v4;
    if ( v4 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v6, v5, L"DeletePushEnableContext: Failed to clear wpm context", v4);
    }
  }
  *((_DWORD *)this + 32) = 0;
  return v2;
}

```

## disassembly

```asm
0x18002666c  mov     r11, rsp
0x18002666f  mov     [r11+10h], rbx
0x180026673  push    rdi
0x180026674  sub     rsp, 60h
0x180026678  mov     rax, cs:__security_cookie
0x18002667f  xor     rax, rsp
0x180026682  mov     [rsp+68h+var_18], rax
0x180026687  mov     eax, [rcx+80h]
0x18002668d  xor     ebx, ebx
0x18002668f  mov     [rsp+68h+var_24], 0
0x180026697  mov     rdi, rcx
0x18002669a  test    eax, eax
0x18002669c  jz      short loc_1800266FA
0x18002669e  mov     [rsp+68h+var_28], eax
0x1800266a2  lea     r9d, [rbx+1Fh]
0x1800266a6  mov     rax, [rcx+88h]
0x1800266ad  lea     r8, NPI_MS_TCP_MODULEID
0x1800266b4  mov     [rsp+68h+var_30], ebx
0x1800266b8  lea     edx, [rbx+3]
0x1800266bb  mov     [r11-38h], rbx
0x1800266bf  lea     ecx, [rbx+1]
0x1800266c2  mov     [r11-20h], rax
0x1800266c6  lea     rax, [r11-28h]
0x1800266ca  mov     [rsp+68h+var_40], 10h
0x1800266d2  mov     [r11-48h], rax
0x1800266d6  call    cs:__imp_NsiSetAllParameters
0x1800266dc  mov     ebx, eax
0x1800266de  test    eax, eax
0x1800266e0  jz      short loc_1800266FA
0x1800266e2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800266e9  jz      short loc_1800266FA
0x1800266eb  mov     r9d, eax
0x1800266ee  lea     r8, aDeletepushenab; "DeletePushEnableContext: Failed to clea"...
0x1800266f5  call    McTemplateU0zq_EventWriteTransfer
0x1800266fa  mov     dword ptr [rdi+80h], 0
0x180026704  mov     eax, ebx
0x180026706  mov     rcx, [rsp+68h+var_18]
0x18002670b  xor     rcx, rsp; StackCookie
0x18002670e  call    __security_check_cookie
0x180026713  mov     rbx, [rsp+68h+arg_8]
0x180026718  add     rsp, 60h
0x18002671c  pop     rdi
0x18002671d  retn
```
