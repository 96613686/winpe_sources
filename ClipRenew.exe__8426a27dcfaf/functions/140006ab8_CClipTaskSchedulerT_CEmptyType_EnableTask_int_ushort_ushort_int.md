# CClipTaskSchedulerT<CEmptyType>::EnableTask(int,ushort *,ushort *,int)

- ea: `0x140006ab8`
- end: `0x140006bef`
- name: `?EnableTask@?$CClipTaskSchedulerT@VCEmptyType@@@@SAJHPEAG0H@Z`
- size: `311`
- prototype: `__int64 __fastcall(int, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140007dcc`

## callees

- `0x140003454`
- `0x140004780`
- `0x140006ab8`
- `0x1400077fc`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140006af9`
- `OLEAUT32!__imp_VariantInit` at `0x140006af9`
- `OLEAUT32!__imp_VariantClear` at `0x140006ba2`
- `OLEAUT32!__imp_VariantClear` at `0x140006ba2`

## pseudocode

```c
__int64 __fastcall CClipTaskSchedulerT<CEmptyType>::EnableTask(int a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int16 v8; // si
  int SchedulerObjects; // eax
  __int64 v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall *v13)(__int64, VARIANTARG *, __int64 *); // rax
  __int64 v15; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+28h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-28h] BYREF
  __int16 v19; // [rsp+B0h] [rbp+38h] BYREF

  v16 = 0;
  v19 = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = -(a1 != 0);
  SchedulerObjects = CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(a2, a3, &v16);
  v10 = v16;
  if ( SchedulerObjects < 0 )
  {
    v12 = 1;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v16 + 80LL))(v16, &v19);
    v12 = v11;
    if ( v11 < 0
      || v8 != v19
      && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 88LL))(v10, v8), v12 = v11, v11 < 0)
      || a4
      && a1
      && (v13 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64 *))(*(_QWORD *)v10 + 96LL),
          v18 = pvarg,
          v11 = v13(v10, &v18, &v15),
          v12 = v11,
          v11 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
    }
  }
  VariantClear(&pvarg);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return v12;
}

```

## disassembly

```asm
0x140006ab8  push    rbp
0x140006aba  push    rbx
0x140006abb  push    rsi
0x140006abc  push    rdi
0x140006abd  push    r14
0x140006abf  push    r15
0x140006ac1  mov     rbp, rsp
0x140006ac4  sub     rsp, 78h
0x140006ac8  xor     eax, eax
0x140006aca  mov     [rbp+var_50], 0
0x140006ad2  mov     r14d, ecx
0x140006ad5  mov     [rbp+arg_0], ax
0x140006ad9  xorps   xmm0, xmm0
0x140006adc  mov     qword ptr [rbp+pvarg+10h], rax
0x140006ae0  lea     rcx, [rbp+pvarg]; pvarg
0x140006ae4  mov     [rbp+var_58], 0
0x140006aec  movups  xmmword ptr [rbp+pvarg], xmm0
0x140006af0  mov     r15d, r9d
0x140006af3  mov     rbx, r8
0x140006af6  mov     rdi, rdx
0x140006af9  call    cs:__imp_VariantInit
0x140006aff  mov     eax, r14d
0x140006b02  lea     r8, [rbp+var_50]
0x140006b06  neg     eax
0x140006b08  mov     rdx, rbx
0x140006b0b  mov     rcx, rdi
0x140006b0e  sbb     si, si
0x140006b11  call    ?GetSchedulerObjects@?$CClipTaskSchedulerT@VCEmptyType@@@@CAJPEAG0PEAPEAUIRegisteredTask@@PEAPEAUITaskFolder@@@Z; CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(ushort *,ushort *,IRegisteredTask * *,ITaskFolder * *)
0x140006b16  mov     rdi, [rbp+var_50]
0x140006b1a  test    eax, eax
0x140006b1c  js      short loc_140006B99
0x140006b1e  mov     rax, [rdi]
0x140006b21  lea     rdx, [rbp+arg_0]
0x140006b25  mov     rcx, rdi
0x140006b28  mov     rax, [rax+50h]
0x140006b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b31  mov     ebx, eax
0x140006b33  test    eax, eax
0x140006b35  jns     short loc_140006B40
0x140006b37  mov     ecx, eax
0x140006b39  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006b3e  jmp     short loc_140006B9E
0x140006b40  cmp     si, [rbp+arg_0]
0x140006b44  jz      short loc_140006B5E
0x140006b46  mov     rax, [rdi]
0x140006b49  movzx   edx, si
0x140006b4c  mov     rcx, rdi
0x140006b4f  mov     rax, [rax+58h]
0x140006b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b58  mov     ebx, eax
0x140006b5a  test    eax, eax
0x140006b5c  js      short loc_140006B37
0x140006b5e  test    r15d, r15d
0x140006b61  jz      short loc_140006B9E
0x140006b63  test    r14d, r14d
0x140006b66  jz      short loc_140006B9E
0x140006b68  mov     rax, [rdi]
0x140006b6b  lea     r8, [rbp+var_58]
0x140006b6f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140006b73  lea     rdx, [rbp+var_28]
0x140006b77  mov     rcx, rdi
0x140006b7a  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140006b7f  mov     rax, [rax+60h]
0x140006b83  movaps  [rbp+var_28], xmm0
0x140006b87  movsd   [rbp+var_18], xmm1
0x140006b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b91  mov     ebx, eax
0x140006b93  test    eax, eax
0x140006b95  jns     short loc_140006B9E
0x140006b97  jmp     short loc_140006B37
0x140006b99  mov     ebx, 1
0x140006b9e  lea     rcx, [rbp+pvarg]; pvarg
0x140006ba2  call    cs:__imp_VariantClear
0x140006ba8  mov     ecx, ebx
0x140006baa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006baf  mov     rcx, [rbp+var_58]
0x140006bb3  test    rcx, rcx
0x140006bb6  jz      short loc_140006BCC
0x140006bb8  mov     rax, [rcx]
0x140006bbb  mov     rax, [rax+10h]
0x140006bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bc4  mov     [rbp+var_58], 0
0x140006bcc  test    rdi, rdi
0x140006bcf  jz      short loc_140006BE0
0x140006bd1  mov     rax, [rdi]
0x140006bd4  mov     rcx, rdi
0x140006bd7  mov     rax, [rax+10h]
0x140006bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006be0  mov     eax, ebx
0x140006be2  add     rsp, 78h
0x140006be6  pop     r15
0x140006be8  pop     r14
0x140006bea  pop     rdi
0x140006beb  pop     rsi
0x140006bec  pop     rbx
0x140006bed  pop     rbp
0x140006bee  retn
```
