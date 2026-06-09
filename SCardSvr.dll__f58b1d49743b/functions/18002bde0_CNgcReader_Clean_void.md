# CNgcReader::Clean(void)

- ea: `0x18002bde0`
- end: `0x18002be8d`
- name: `?Clean@CNgcReader@@IEAAXXZ`
- size: `173`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b43c`
- `0x18002bea0`

## callees

- `0x1800151f8`
- `0x18002b6e0`
- `0x18002bbb4`
- `0x1800326d0`

## string_xrefs

- `0x18002be05`: `CNgcReader::Clean`

## pseudocode

```c
void __fastcall CNgcReader::Clean(CNgcReader *this)
{
  int v2; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v3; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-30h] BYREF
  char v5[24]; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  v4[0] = v5;
  v4[1] = &v2;
  strcpy(v5, "CNgcReader::Clean");
  lambda_f0c8e681ce0fa3da83d5eebe59d305b7_::operator()(v4);
  v2 = 1;
  v3 = v4;
  Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close((char *)this + 872);
  *((_DWORD *)this + 198) = 0;
  *((_DWORD *)this + 204) = 0;
  *(_OWORD *)((char *)this + 760) = 0;
  WppTraceUnwinder__lambda_f0c8e681ce0fa3da83d5eebe59d305b7____::_WppTraceUnwinder__lambda_f0c8e681ce0fa3da83d5eebe59d305b7____(&v3);
}

```

## disassembly

```asm
0x18002bde0  mov     [rsp-8+arg_8], rbx
0x18002bde5  push    rbp
0x18002bde6  mov     rbp, rsp
0x18002bde9  sub     rsp, 60h
0x18002bded  mov     rax, cs:__security_cookie
0x18002bdf4  xor     rax, rsp
0x18002bdf7  mov     [rbp+var_8], rax
0x18002bdfb  movzx   eax, word ptr cs:aCngcreaderClea+10h; "n"
0x18002be02  mov     rbx, rcx
0x18002be05  movups  xmm0, xmmword ptr cs:aCngcreaderClea; "CNgcReader::Clean"
0x18002be0c  mov     word ptr [rbp+var_20+10h], ax
0x18002be10  lea     rcx, [rbp+var_30]
0x18002be14  lea     rax, [rbp+var_20]
0x18002be18  mov     [rbp+var_40], 0
0x18002be1f  mov     [rbp+var_30], rax
0x18002be23  lea     rax, [rbp+var_40]
0x18002be27  mov     [rbp+var_28], rax
0x18002be2b  movups  xmmword ptr [rbp+var_20], xmm0
0x18002be2f  call    _lambda_f0c8e681ce0fa3da83d5eebe59d305b7___operator__
0x18002be34  lea     rax, [rbp+var_30]
0x18002be38  mov     [rbp+var_40], 1
0x18002be3f  lea     rcx, [rbx+368h]
0x18002be46  mov     [rbp+var_38], rax
0x18002be4a  call    ?Close@?$HandleT@UNgcRpcContextTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<NgcRpcContextTraits>::Close(void)
0x18002be4f  mov     dword ptr [rbx+318h], 0
0x18002be59  lea     rcx, [rbp+var_38]
0x18002be5d  xorps   xmm0, xmm0
0x18002be60  mov     dword ptr [rbx+330h], 0
0x18002be6a  movups  xmmword ptr [rbx+2F8h], xmm0
0x18002be71  call    WppTraceUnwinder__lambda_f0c8e681ce0fa3da83d5eebe59d305b7_______WppTraceUnwinder__lambda_f0c8e681ce0fa3da83d5eebe59d305b7____
0x18002be76  mov     rcx, [rbp+var_8]
0x18002be7a  xor     rcx, rsp; StackCookie
0x18002be7d  call    __security_check_cookie
0x18002be82  mov     rbx, [rsp+60h+arg_8]
0x18002be87  add     rsp, 60h
0x18002be8b  pop     rbp
0x18002be8c  retn
```
