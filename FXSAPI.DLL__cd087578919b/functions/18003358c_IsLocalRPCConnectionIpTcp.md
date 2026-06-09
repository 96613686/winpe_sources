# IsLocalRPCConnectionIpTcp

- ea: `0x18003358c`
- end: `0x180033660`
- name: `IsLocalRPCConnectionIpTcp`
- size: `212`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, _DWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180009ba0`
- `0x180009dd0`
- `0x18000a140`
- `0x18000a2c0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002bb58`
- `0x1800332d8`
- `0x18003358c`
- `0x18003d4d6`

## pseudocode

```c
__int64 __fastcall IsLocalRPCConnectionIpTcp(RPC_BINDING_HANDLE ClientBinding, _DWORD *a2)
{
  unsigned int RpcStringBindingInfo; // eax
  unsigned int v5; // ebx
  wchar_t *v7; // rbx
  wchar_t *String1; // [rsp+40h] [rbp+18h] BYREF

  String1 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cd83264e607130c79307a35de44658c9_Traceguids);
  }
  RpcStringBindingInfo = GetRpcStringBindingInfo(ClientBinding, &String1, 0);
  v5 = RpcStringBindingInfo;
  if ( RpcStringBindingInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_cd83264e607130c79307a35de44658c9_Traceguids,
        RpcStringBindingInfo);
    }
    return v5;
  }
  else
  {
    v7 = String1;
    *a2 = wcscmp_0(String1, L"127.0.0.1") == 0;
    pMemFree(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18003358c  mov     [rsp+arg_0], rbx
0x180033591  mov     [rsp+arg_8], rbp
0x180033596  push    rdi
0x180033597  sub     rsp, 20h
0x18003359b  mov     rdi, rdx
0x18003359e  mov     [rsp+28h+String1], 0
0x1800335a7  mov     rbx, rcx
0x1800335aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335b1  lea     rbp, WPP_GLOBAL_Control
0x1800335b8  cmp     rcx, rbp
0x1800335bb  jz      short loc_1800335DE
0x1800335bd  test    byte ptr [rcx+1Ch], 2
0x1800335c1  jz      short loc_1800335DE
0x1800335c3  cmp     byte ptr [rcx+19h], 5
0x1800335c7  jb      short loc_1800335DE
0x1800335c9  mov     rcx, [rcx+10h]
0x1800335cd  lea     r8, WPP_cd83264e607130c79307a35de44658c9_Traceguids
0x1800335d4  mov     edx, 12h
0x1800335d9  call    WPP_SF_
0x1800335de  xor     r8d, r8d
0x1800335e1  lea     rdx, [rsp+28h+String1]
0x1800335e6  mov     rcx, rbx; ClientBinding
0x1800335e9  call    GetRpcStringBindingInfo
0x1800335ee  mov     ebx, eax
0x1800335f0  test    eax, eax
0x1800335f2  jz      short loc_180033628
0x1800335f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335fb  cmp     rcx, rbp
0x1800335fe  jz      short loc_180033624
0x180033600  test    byte ptr [rcx+1Ch], 2
0x180033604  jz      short loc_180033624
0x180033606  cmp     byte ptr [rcx+19h], 2
0x18003360a  jb      short loc_180033624
0x18003360c  mov     rcx, [rcx+10h]
0x180033610  lea     r8, WPP_cd83264e607130c79307a35de44658c9_Traceguids
0x180033617  mov     edx, 13h
0x18003361c  mov     r9d, eax
0x18003361f  call    WPP_SF_d
0x180033624  mov     eax, ebx
0x180033626  jmp     short loc_18003364F
0x180033628  mov     rbx, [rsp+28h+String1]
0x18003362d  lea     rdx, a127001; "127.0.0.1"
0x180033634  mov     rcx, rbx; String1
0x180033637  call    wcscmp_0
0x18003363c  xor     edx, edx
0x18003363e  mov     rcx, rbx; lpMem
0x180033641  test    eax, eax
0x180033643  setz    dl
0x180033646  mov     [rdi], edx
0x180033648  call    pMemFree
0x18003364d  xor     eax, eax
0x18003364f  mov     rbx, [rsp+28h+arg_0]
0x180033654  mov     rbp, [rsp+28h+arg_8]
0x180033659  add     rsp, 20h
0x18003365d  pop     rdi
0x18003365e  retn
```
