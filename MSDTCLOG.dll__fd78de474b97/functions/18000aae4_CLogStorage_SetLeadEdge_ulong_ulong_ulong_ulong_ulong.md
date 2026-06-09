# CLogStorage::SetLeadEdge(ulong,ulong,ulong,ulong,ulong)

- ea: `0x18000aae4`
- end: `0x18000abce`
- name: `?SetLeadEdge@CLogStorage@@QEAAXKKKKK@Z`
- size: `234`
- prototype: `void __usercall(CLogStorage *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006328`

## callees

- `0x18000aae4`
- `0x18000b974`
- `0x18000d998`
- `0x18001266c`
- `0x1800127f2`

## string_xrefs

- `0x18000ab9c`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogStorage::SetLeadEdge(
        CLogStorage *this,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  int v7; // esi
  struct CBuffer *v8; // rax
  bool v9; // zf
  _DWORD *v10; // rbx
  ulong pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  v7 = a2;
  if ( a4 == 0x8000 && *((_DWORD *)this + 10) + 0x8000 < a3 )
  {
    ++*(_DWORD *)this;
    v7 = a2 + 1;
  }
  v8 = CLogStorage::_MapBuffer(this, a4, *((_DWORD *)this + 10), 0, 0);
  v9 = *((_DWORD *)this + 31) == 0;
  *((_QWORD *)this + 12) = v8;
  v10 = (_DWORD *)*((_QWORD *)v8 + 3);
  if ( v9 )
  {
    memcpy_0(
      v10,
      *(const void **)(*(_QWORD *)((char *)this + (-(__int64)(*((_DWORD *)this + 30) != 0) & 0xFFFFFFFFFFFFFFF8uLL)
                                                + 136)
                     + 24LL),
      0x2000u);
    if ( v10[2] != v7 || v10[6] != a6 || v10[7] != a5 )
    {
      TraceFile(
        -1073737670,
        "IDS_DTC_E_LOG_CORRUPT_ERROR",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp",
        956);
      pExceptionObject = -1073737670;
      throw &pExceptionObject;
    }
  }
  else
  {
    v10[6] = a6;
    v10[7] = a5;
  }
}

```

## disassembly

```asm
0x18000aae4  mov     [rsp+arg_0], rbx
0x18000aae9  mov     [rsp+arg_8], rsi
0x18000aaee  push    rdi
0x18000aaef  sub     rsp, 30h
0x18000aaf3  mov     rdi, rcx
0x18000aaf6  mov     r10d, r9d
0x18000aaf9  mov     ecx, 8000h
0x18000aafe  mov     esi, edx
0x18000ab00  cmp     r9d, ecx
0x18000ab03  jnz     short loc_18000AB13
0x18000ab05  mov     eax, [rdi+28h]
0x18000ab08  add     eax, ecx
0x18000ab0a  cmp     eax, r8d
0x18000ab0d  jnb     short loc_18000AB13
0x18000ab0f  inc     dword ptr [rdi]
0x18000ab11  inc     esi
0x18000ab13  mov     r8d, [rdi+28h]; unsigned int
0x18000ab17  xor     r9d, r9d; int
0x18000ab1a  mov     edx, r10d; unsigned int
0x18000ab1d  mov     [rsp+38h+var_18], 0; unsigned int
0x18000ab25  mov     rcx, rdi; this
0x18000ab28  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000ab2d  cmp     dword ptr [rdi+7Ch], 0
0x18000ab31  mov     [rdi+60h], rax
0x18000ab35  mov     rbx, [rax+18h]
0x18000ab39  jz      short loc_18000AB59
0x18000ab3b  mov     eax, [rsp+38h+arg_28]
0x18000ab3f  mov     [rbx+18h], eax
0x18000ab42  mov     eax, [rsp+38h+arg_20]
0x18000ab46  mov     [rbx+1Ch], eax
0x18000ab49  mov     rbx, [rsp+38h+arg_0]
0x18000ab4e  mov     rsi, [rsp+38h+arg_8]
0x18000ab53  add     rsp, 30h
0x18000ab57  pop     rdi
0x18000ab58  retn
0x18000ab59  mov     eax, [rdi+78h]
0x18000ab5c  mov     r8d, 2000h; Size
0x18000ab62  neg     eax
0x18000ab64  mov     rcx, rbx; void *
0x18000ab67  sbb     rdx, rdx
0x18000ab6a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000ab6e  mov     rdx, [rdx+rdi+88h]
0x18000ab76  mov     rdx, [rdx+18h]; Src
0x18000ab7a  call    memcpy_0
0x18000ab7f  cmp     [rbx+8], esi
0x18000ab82  jnz     short loc_18000AB96
0x18000ab84  mov     eax, [rsp+38h+arg_28]
0x18000ab88  cmp     [rbx+18h], eax
0x18000ab8b  jnz     short loc_18000AB96
0x18000ab8d  mov     eax, [rsp+38h+arg_20]
0x18000ab91  cmp     [rbx+1Ch], eax
0x18000ab94  jz      short loc_18000AB49
0x18000ab96  mov     r9d, 3BCh; unsigned int
0x18000ab9c  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000aba3  lea     rdx, aIdsDtcELogCorr; "IDS_DTC_E_LOG_CORRUPT_ERROR"
0x18000abaa  mov     ecx, 0C000103Ah; int
0x18000abaf  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000abb4  lea     rdx, _TI1K; pThrowInfo
0x18000abbb  mov     [rsp+38h+pExceptionObject], 0C000103Ah
0x18000abc3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000abc8  call    _CxxThrowException_0
```
