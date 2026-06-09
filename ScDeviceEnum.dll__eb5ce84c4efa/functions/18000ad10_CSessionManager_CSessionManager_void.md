# CSessionManager::~CSessionManager(void)

- ea: `0x18000ad10`
- end: `0x18000adb3`
- name: `??1CSessionManager@@QEAA@XZ`
- size: `163`
- prototype: `void __fastcall(CSessionManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f600`

## callees

- `0x18000ac20`
- `0x18000ac74`
- `0x18000b19c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ad8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ad8b`

## pseudocode

```c
void __fastcall CSessionManager::~CSessionManager(CSessionManager *this)
{
  int v2; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v3; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
  char v5[40]; // [rsp+40h] [rbp-30h] BYREF

  v4[0] = v5;
  v2 = 0;
  v4[1] = &v2;
  strcpy(v5, "CSessionManager::~CSessionManager");
  lambda_b7c29d5e8583b411c126f68f14b07015_::operator()(v4);
  v2 = 1;
  v3 = v4;
  WppTraceUnwinder__lambda_b7c29d5e8583b411c126f68f14b07015____::_WppTraceUnwinder__lambda_b7c29d5e8583b411c126f68f14b07015____(&v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>(this);
}

```

## disassembly

```asm
0x18000ad10  mov     [rsp-8+arg_8], rbx
0x18000ad15  push    rbp
0x18000ad16  mov     rbp, rsp
0x18000ad19  sub     rsp, 70h
0x18000ad1d  mov     rax, cs:__security_cookie
0x18000ad24  xor     rax, rsp
0x18000ad27  mov     [rbp+var_8], rax
0x18000ad2b  movzx   eax, word ptr cs:aCsessionmanage_3+20h; "r"
0x18000ad32  mov     rbx, rcx
0x18000ad35  movups  xmm0, xmmword ptr cs:aCsessionmanage_3; "CSessionManager::~CSessionManager"
0x18000ad3c  mov     word ptr [rbp+var_30+20h], ax
0x18000ad40  lea     rax, [rbp+var_30]
0x18000ad44  movups  xmm1, xmmword ptr cs:aCsessionmanage_3+10h; ":~CSessionManager"
0x18000ad4b  mov     [rbp+var_40], rax
0x18000ad4f  lea     rcx, [rbp+var_40]
0x18000ad53  lea     rax, [rbp+var_50]
0x18000ad57  mov     [rbp+var_50], 0
0x18000ad5e  mov     [rbp+var_38], rax
0x18000ad62  movups  xmmword ptr [rbp+var_30], xmm0
0x18000ad66  movups  xmmword ptr [rbp+var_30+10h], xmm1
0x18000ad6a  call    _lambda_b7c29d5e8583b411c126f68f14b07015___operator__
0x18000ad6f  lea     rax, [rbp+var_40]
0x18000ad73  mov     [rbp+var_50], 1
0x18000ad7a  lea     rcx, [rbp+var_48]
0x18000ad7e  mov     [rbp+var_48], rax
0x18000ad82  call    WppTraceUnwinder__lambda_b7c29d5e8583b411c126f68f14b07015_______WppTraceUnwinder__lambda_b7c29d5e8583b411c126f68f14b07015____
0x18000ad87  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000ad8b  call    cs:__imp_DeleteCriticalSection
0x18000ad91  mov     rcx, rbx
0x18000ad94  call    ??1?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>(void)
0x18000ad99  mov     rcx, [rbp+var_8]
0x18000ad9d  xor     rcx, rsp; StackCookie
0x18000ada0  call    __security_check_cookie
0x18000ada5  mov     rbx, [rsp+70h+arg_8]
0x18000adad  add     rsp, 70h
0x18000adb1  pop     rbp
0x18000adb2  retn
```
