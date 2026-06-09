# NamedPipeChannel::StartConnection(void)

- ea: `0x1800762b0`
- end: `0x180076340`
- name: `?StartConnection@NamedPipeChannel@@UEAAXXZ`
- size: `144`
- prototype: `void __fastcall(NamedPipeChannel *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800125c0`
- `0x180016250`
- `0x180043a8c`
- `0x1800759c0`
- `0x1800762b0`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180076339`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180076339`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800762eb`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800762eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NamedPipeChannel::StartConnection(NamedPipeChannel *this)
{
  _QWORD *v2; // rax
  __int64 v3; // [rsp+30h] [rbp-18h] BYREF
  _DWORD v4[4]; // [rsp+38h] [rbp-10h] BYREF
  _QWORD *v5; // [rsp+50h] [rbp+8h] BYREF

  v2 = operator new(8u);
  *v2 = this;
  v5 = v2;
  v3 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____0_,
         v2,
         0,
         v4);
  if ( !v3 )
  {
    v4[0] = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18007633FLL);
  }
  v5 = 0;
  std::unique_ptr_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____std::default_delete_std::tuple__lambda_1ad8bec329c890e3e1881878130943db_______::_unique_ptr_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____std::default_delete_std::tuple__lambda_1ad8bec329c890e3e1881878130943db_______(&v5);
  std::thread::operator=((char *)this + 8, &v3);
  std::thread::~thread((std::thread *)&v3);
}

```

## disassembly

```asm
0x1800762b0  push    rbx
0x1800762b2  sub     rsp, 40h
0x1800762b6  mov     rbx, rcx
0x1800762b9  mov     ecx, 8; Size
0x1800762be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800762c3  mov     [rax], rbx
0x1800762c6  mov     [rsp+48h+arg_0], rax
0x1800762cb  lea     rcx, [rsp+48h+var_10]
0x1800762d0  mov     [rsp+48h+var_20], rcx
0x1800762d5  mov     [rsp+48h+var_28], 0
0x1800762dd  mov     r9, rax
0x1800762e0  lea     r8, std__thread___Invoke_std__tuple__lambda_1ad8bec329c890e3e1881878130943db____0_
0x1800762e7  xor     edx, edx
0x1800762e9  xor     ecx, ecx
0x1800762eb  call    cs:__imp__o__beginthreadex
0x1800762f1  mov     [rsp+48h+var_18], rax
0x1800762f6  test    rax, rax
0x1800762f9  jz      short loc_18007632C
0x1800762fb  mov     [rsp+48h+arg_0], 0
0x180076304  lea     rcx, [rsp+48h+arg_0]
0x180076309  call    std__unique_ptr_std__tuple__lambda_1ad8bec329c890e3e1881878130943db____std__default_delete_std__tuple__lambda_1ad8bec329c890e3e1881878130943db__________unique_ptr_std__tuple__lambda_1ad8bec329c890e3e1881878130943db____std__default_delete_std__tuple__lambda_1ad8bec329c890e3e1881878130943db_______
0x18007630e  lea     rcx, [rbx+8]
0x180076312  lea     rdx, [rsp+48h+var_18]
0x180076317  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18007631c  lea     rcx, [rsp+48h+var_18]; this
0x180076321  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180076326  add     rsp, 40h
0x18007632a  pop     rbx
0x18007632b  retn
0x18007632c  mov     [rsp+48h+var_10], 0
0x180076334  mov     ecx, 6
0x180076339  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
