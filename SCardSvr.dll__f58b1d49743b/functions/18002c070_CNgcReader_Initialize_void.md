# CNgcReader::Initialize(void)

- ea: `0x18002c070`
- end: `0x18002c14b`
- name: `?Initialize@CNgcReader@@UEAAXXZ`
- size: `219`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800037b8`
- `0x180003ff0`
- `0x180006700`
- `0x18000f770`
- `0x18001a748`
- `0x18002ab4c`
- `0x18002b6a8`
- `0x18002bafc`
- `0x18002d870`
- `0x1800326d0`

## string_xrefs

- `0x18002c095`: `CNgcReader::Initialize`

## pseudocode

```c
void __fastcall CNgcReader::Initialize(CNgcReader *this)
{
  int v2; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v3; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
  CReader *v5[2]; // [rsp+40h] [rbp-30h] BYREF
  char v6[24]; // [rsp+50h] [rbp-20h] BYREF

  v2 = 0;
  strcpy(v6, "CNgcReader::Initialize");
  v4[0] = v6;
  v4[1] = &v2;
  lambda_8ea29733fd4a6f255f41929acdd8161a_::operator()(v4);
  v2 = 1;
  v3 = v4;
  CNgcReader::InitializeReaderInformation(this);
  CReader::Initialize(this);
  *((_DWORD *)this + 8) = 0;
  CReader::SetAvailabilityStatusLocked(this, 2);
  CLatchReader::CLatchReader((CLatchReader *)v5, this, 0);
  CReader::PowerUp(this);
  CMultiEvent::Signal(g_phReaderChangeEvent);
  CLatchReader::~CLatchReader(v5);
  WppTraceUnwinder__lambda_8ea29733fd4a6f255f41929acdd8161a____::_WppTraceUnwinder__lambda_8ea29733fd4a6f255f41929acdd8161a____(&v3);
}

```

## disassembly

```asm
0x18002c070  mov     [rsp-8+arg_8], rbx
0x18002c075  push    rbp
0x18002c076  mov     rbp, rsp
0x18002c079  sub     rsp, 70h
0x18002c07d  mov     rax, cs:__security_cookie
0x18002c084  xor     rax, rsp
0x18002c087  mov     [rbp+var_8], rax
0x18002c08b  mov     rbx, rcx
0x18002c08e  mov     [rbp+var_50], 0
0x18002c095  movups  xmm0, xmmword ptr cs:aCngcreaderInit_0; "CNgcReader::Initialize"
0x18002c09c  movups  xmmword ptr [rbp+var_20], xmm0
0x18002c0a0  movsd   xmm1, qword ptr cs:aCngcreaderInit_0+0Fh; "tialize"
0x18002c0a8  movsd   qword ptr [rbp+var_20+0Fh], xmm1
0x18002c0ad  lea     rax, [rbp+var_20]
0x18002c0b1  mov     [rbp+var_40], rax
0x18002c0b5  lea     rax, [rbp+var_50]
0x18002c0b9  mov     [rbp+var_38], rax
0x18002c0bd  lea     rcx, [rbp+var_40]
0x18002c0c1  call    _lambda_8ea29733fd4a6f255f41929acdd8161a___operator__
0x18002c0c6  mov     [rbp+var_50], 1
0x18002c0cd  lea     rax, [rbp+var_40]
0x18002c0d1  mov     [rbp+var_48], rax
0x18002c0d5  mov     rcx, rbx; this
0x18002c0d8  call    ?InitializeReaderInformation@CNgcReader@@IEAAXXZ; CNgcReader::InitializeReaderInformation(void)
0x18002c0dd  mov     rcx, rbx; this
0x18002c0e0  call    ?Initialize@CReader@@UEAAXXZ; CReader::Initialize(void)
0x18002c0e5  mov     dword ptr [rbx+20h], 0
0x18002c0ec  mov     edx, 2
0x18002c0f1  mov     rcx, rbx
0x18002c0f4  call    ?SetAvailabilityStatusLocked@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatusLocked(CReader::AvailableState)
0x18002c0f9  xor     r8d, r8d; struct CReader::ActiveState *
0x18002c0fc  mov     rdx, rbx; struct CReader *
0x18002c0ff  lea     rcx, [rbp+var_30]; this
0x18002c103  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x18002c108  nop
0x18002c109  mov     rcx, rbx; this
0x18002c10c  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18002c111  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x18002c118  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x18002c11d  nop
0x18002c11e  lea     rcx, [rbp+var_30]; this
0x18002c122  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x18002c127  nop
0x18002c128  lea     rcx, [rbp+var_48]
0x18002c12c  call    WppTraceUnwinder__lambda_8ea29733fd4a6f255f41929acdd8161a_______WppTraceUnwinder__lambda_8ea29733fd4a6f255f41929acdd8161a____
0x18002c131  mov     rcx, [rbp+var_8]
0x18002c135  xor     rcx, rsp; StackCookie
0x18002c138  call    __security_check_cookie
0x18002c13d  mov     rbx, [rsp+70h+arg_8]
0x18002c145  add     rsp, 70h
0x18002c149  pop     rbp
0x18002c14a  retn
```
