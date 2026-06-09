# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ParseArgumentsKey(ushort const *,WindowsInternal::ApplicationModel::Calls::IncomingToastAction *,uint *)

- ea: `0x1800147b0`
- end: `0x18001482f`
- name: `?_ParseArgumentsKey@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBGPEAW4IncomingToastAction@234@PEAI@Z`
- size: `127`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this, const unsigned __int16 *, enum WindowsInternal::ApplicationModel::Calls::IncomingToastAction *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800028d0`
- `0x1800147b0`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_ParseArgumentsKey(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        const unsigned __int16 *a2,
        enum WindowsInternal::ApplicationModel::Calls::IncomingToastAction *a3,
        unsigned int *a4)
{
  int v6; // eax
  unsigned int v7; // ecx
  __int64 result; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-14h] BYREF

  v10 = 0;
  v9 = 0;
  v6 = swscanf_s(a2, L"%u.%u", &v9, &v10);
  v7 = v9;
  if ( v6 != 2 && v9 < 7 )
    return 2147942487LL;
  *a4 = v10;
  result = 0;
  *(_DWORD *)a3 = v7;
  return result;
}

```

## disassembly

```asm
0x1800147b0  mov     [rsp+arg_0], rbx
0x1800147b5  push    rdi
0x1800147b6  sub     rsp, 30h
0x1800147ba  mov     rax, cs:__security_cookie
0x1800147c1  xor     rax, rsp
0x1800147c4  mov     [rsp+38h+var_10], rax
0x1800147c9  mov     rdi, r9
0x1800147cc  mov     [rsp+38h+var_14], 0
0x1800147d4  mov     rbx, r8
0x1800147d7  mov     [rsp+38h+var_18], 0
0x1800147df  mov     rcx, rdx; Buffer
0x1800147e2  lea     r9, [rsp+38h+var_14]
0x1800147e7  lea     r8, [rsp+38h+var_18]
0x1800147ec  lea     rdx, aUU; "%u.%u"
0x1800147f3  call    swscanf_s
0x1800147f8  mov     ecx, [rsp+38h+var_18]
0x1800147fc  cmp     eax, 2
0x1800147ff  jz      short loc_18001480D
0x180014801  cmp     ecx, 7
0x180014804  jnb     short loc_18001480D
0x180014806  mov     eax, 80070057h
0x18001480b  jmp     short loc_180014817
0x18001480d  mov     eax, [rsp+38h+var_14]
0x180014811  mov     [rdi], eax
0x180014813  xor     eax, eax
0x180014815  mov     [rbx], ecx
0x180014817  mov     rcx, [rsp+38h+var_10]
0x18001481c  xor     rcx, rsp; StackCookie
0x18001481f  call    __security_check_cookie
0x180014824  mov     rbx, [rsp+38h+arg_0]
0x180014829  add     rsp, 30h
0x18001482d  pop     rdi
0x18001482e  retn
```
