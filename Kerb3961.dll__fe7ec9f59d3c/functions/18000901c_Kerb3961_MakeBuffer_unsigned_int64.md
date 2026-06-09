# Kerb3961::MakeBuffer(unsigned __int64)

- ea: `0x18000901c`
- end: `0x18000909c`
- name: `?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `33`
- callee_count: `4`
- tags: ``

## callers

- `0x180004b40`
- `0x180004cf4`
- `0x180004e74`
- `0x180004fac`
- `0x1800050e0`
- `0x180006270`
- `0x180006ac0`
- `0x180007650`
- `0x1800085cc`
- `0x180008a5c`
- `0x1800090b0`
- `0x18000ca80`
- `0x18000e320`
- `0x18000e6c4`
- `0x18000ec30`
- `0x18000f030`
- `0x18000f580`
- `0x18000f754`
- `0x180010f4c`
- `0x1800110c0`
- `0x1800126e0`
- `0x1800130b0`
- `0x1800147a0`
- `0x180014950`
- `0x180016e60`
- `0x1800190d0`
- `0x18001a34c`
- `0x18001a538`
- `0x18001aaf0`
- `0x18001ade0`
- `0x18001b770`
- `0x18001b910`
- `0x18001c130`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x1800048b0`
- `0x18000901c`

## pseudocode

```c
__int64 __fastcall Kerb3961::MakeBuffer(__int64 a1, unsigned __int64 a2)
{
  const char *v4; // rdx
  void *v5; // rdi
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  utl::make_unique<unsigned char [0],0>(&v7, a2);
  v5 = v7;
  if ( v7 )
  {
    *(_QWORD *)a1 = a2;
    *(_QWORD *)(a1 + 8) = v5;
    *(_DWORD *)(a1 + 16) = 0;
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"buffer", v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741801;
  }
  return a1;
}

```

## disassembly

```asm
0x18000901c  mov     [rsp+arg_0], rbx
0x180009021  mov     [rsp+arg_8], rsi
0x180009026  push    rdi
0x180009027  sub     rsp, 20h
0x18000902b  mov     rbx, rcx
0x18000902e  mov     rsi, rdx
0x180009031  lea     rcx, [rsp+28h+arg_10]
0x180009036  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000903b  mov     rdi, [rsp+28h+arg_10]
0x180009040  test    rdi, rdi
0x180009043  setnz   al
0x180009046  test    al, al
0x180009048  jnz     short loc_18000907B
0x18000904a  lea     rcx, aBuffer; "buffer"
0x180009051  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009056  mov     qword ptr [rbx], 0
0x18000905d  mov     qword ptr [rbx+8], 0
0x180009065  mov     dword ptr [rbx+10h], 0C0000017h
0x18000906c  test    rdi, rdi
0x18000906f  jz      short loc_180009089
0x180009071  mov     rcx, rdi; void *
0x180009074  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009079  jmp     short loc_180009089
0x18000907b  mov     [rbx], rsi
0x18000907e  mov     [rbx+8], rdi
0x180009082  mov     dword ptr [rbx+10h], 0
0x180009089  mov     rsi, [rsp+28h+arg_8]
0x18000908e  mov     rax, rbx
0x180009091  mov     rbx, [rsp+28h+arg_0]
0x180009096  add     rsp, 20h
0x18000909a  pop     rdi
0x18000909b  retn
```
