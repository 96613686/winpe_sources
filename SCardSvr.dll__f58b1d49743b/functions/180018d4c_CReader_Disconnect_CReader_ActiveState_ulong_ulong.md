# CReader::Disconnect(CReader::ActiveState *,ulong,ulong *)

- ea: `0x180018d4c`
- end: `0x180018f7b`
- name: `?Disconnect@CReader@@QEAAXPEAUActiveState@1@KPEAK@Z`
- size: `559`
- prototype: `void __fastcall(CReader *__hidden this, struct CReader::ActiveState *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x180005b2c`
- `0x1800106f0`
- `0x180032d50`

## callees

- `0x18000366c`
- `0x18000371c`
- `0x1800044e0`
- `0x180006700`
- `0x18000d7a0`
- `0x18000d9c0`
- `0x18000ecb0`
- `0x18000f770`
- `0x18000f800`
- `0x180010390`
- `0x180015558`
- `0x180018d4c`
- `0x180019bc4`
- `0x18003261b`

## pseudocode

```c
void __fastcall CReader::Disconnect(CReader *this, struct CReader::ActiveState *a2, unsigned int a3, unsigned int *a4)
{
  CReader *v4; // rbx
  const struct CReader::ActiveState *v5; // rsi
  int v6; // edi
  const unsigned __int16 *v7; // r9
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  unsigned __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  CReader *v18; // rdi
  ulong v19; // ecx
  int v20; // [rsp+30h] [rbp-58h]
  ulong pExceptionObject; // [rsp+34h] [rbp-54h] BYREF
  ulong v22; // [rsp+38h] [rbp-50h] BYREF
  ulong v23; // [rsp+3Ch] [rbp-4Ch] BYREF
  ulong v24; // [rsp+40h] [rbp-48h] BYREF
  CReader *v25[2]; // [rsp+48h] [rbp-40h] BYREF
  CReader *v26; // [rsp+58h] [rbp-30h]
  ulong v27; // [rsp+60h] [rbp-28h] BYREF

  try
  {
    v5 = a2;
    v4 = this;
    v26 = this;
    CReader::VerifyActive(this, a2);
    v6 = 1;
    v20 = 1;
  }
  catch ( ulong v23 )
  {
    v19 = v23;
    *a4 = v23;
    a3 = 0;
    if ( v19 == -2146435049 || (v20 = 2, v19 != -2146434968) )
      v20 = 3;
    v4 = this;
    v5 = a2;
    v6 = v20;
  }
  v5 = a2;
  v4 = this;
  v26 = this;
  CReader::VerifyActive(this, a2);
  v6 = 1;
  v20 = 1;
}

```

## disassembly

```asm
0x180018d4c  mov     rax, rsp
0x180018d4f  mov     [rax+20h], r9
0x180018d53  mov     [rax+18h], r8d
0x180018d57  mov     [rax+10h], rdx
0x180018d5b  mov     [rax+8], rcx
0x180018d5f  push    rbx
0x180018d60  push    rsi
0x180018d61  push    rdi
0x180018d62  sub     rsp, 70h
0x180018d66  mov     rsi, rdx
0x180018d69  mov     rbx, rcx
0x180018d6c  mov     [rsp+88h+var_30], rcx
0x180018d71  call    ?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::VerifyActive(CReader::ActiveState const *)
0x180018d76  mov     edi, 1
0x180018d7b  mov     [rsp+88h+var_58], edi
0x180018d7f  jmp     short loc_180018D95
0x180018d81  mov     rbx, [rsp+88h+arg_0]
0x180018d89  mov     rsi, [rsp+88h+arg_8]
0x180018d91  mov     edi, [rsp+88h+var_58]
0x180018d95  lea     rdx, [rbx+38h]; struct CAccessLock *
0x180018d99  lea     rcx, [rsp+88h+var_40]; this
0x180018d9e  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x180018da3  nop
0x180018da4  mov     ecx, [rbx+0C0h]
0x180018daa  cmp     ecx, 6
0x180018dad  jg      short loc_180018E1F
0x180018daf  jz      short loc_180018DE3
0x180018db1  sub     ecx, 1
0x180018db4  jz      short loc_180018DCA
0x180018db6  sub     ecx, 1
0x180018db9  jz      short loc_180018DCA
0x180018dbb  sub     ecx, 1
0x180018dbe  jz      short loc_180018DCA
0x180018dc0  sub     ecx, 1
0x180018dc3  jz      short loc_180018DCA
0x180018dc5  cmp     ecx, 1
0x180018dc8  jnz     short loc_180018E3C
0x180018dca  mov     [rsp+88h+pExceptionObject], 80100069h
0x180018dd2  lea     rdx, _TI1K; pThrowInfo
0x180018dd9  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180018dde  call    _CxxThrowException_0
0x180018de3  mov     ecx, edi
0x180018de5  sub     ecx, 1
0x180018de8  jz      short loc_180018DF3
0x180018dea  cmp     ecx, 1
0x180018ded  jnz     loc_180018ED3
0x180018df3  mov     eax, [rbx+0E0h]
0x180018df9  test    eax, eax
0x180018dfb  jz      short loc_180018E0D
0x180018dfd  dec     eax
0x180018dff  mov     [rbx+0E0h], eax
0x180018e05  test    eax, eax
0x180018e07  jnz     loc_180018ED3
0x180018e0d  mov     edx, 5
0x180018e12  mov     rcx, rbx
0x180018e15  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180018e1a  jmp     loc_180018ED3
0x180018e1f  sub     ecx, 7
0x180018e22  jz      loc_180018EAE
0x180018e28  sub     ecx, 1
0x180018e2b  jz      short loc_180018E8D
0x180018e2d  sub     ecx, 1
0x180018e30  jz      short loc_180018E62
0x180018e32  sub     ecx, 1; unsigned __int8 *
0x180018e35  jz      short loc_180018E62
0x180018e37  cmp     ecx, 1
0x180018e3a  jz      short loc_180018E62
0x180018e3c  xor     r8d, r8d; unsigned __int16 *
0x180018e3f  mov     edx, 193h; unsigned int
0x180018e44  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180018e49  mov     [rsp+88h+var_50], 80100001h
0x180018e51  lea     rdx, _TI1K; pThrowInfo
0x180018e58  lea     rcx, [rsp+88h+var_50]; pExceptionObject
0x180018e5d  call    _CxxThrowException_0
0x180018e62  mov     ecx, edi
0x180018e64  sub     ecx, 1
0x180018e67  jz      short loc_180018E6E
0x180018e69  cmp     ecx, 1
0x180018e6c  jnz     short loc_180018ED3
0x180018e6e  cmp     qword ptr [rbx+0D8h], 0
0x180018e76  jz      short loc_180018E85
0x180018e78  mov     qword ptr [rbx+0D8h], 0
0x180018e83  jmp     short loc_180018ED3
0x180018e85  dec     dword ptr [rbx+0E0h]
0x180018e8b  jmp     short loc_180018ED3
0x180018e8d  mov     qword ptr [rbx+0D8h], 0
0x180018e98  mov     dword ptr [rbx+0ECh], 0
0x180018ea2  mov     dword ptr [rbx+0C0h], 0
0x180018eac  jmp     short loc_180018ED3
0x180018eae  mov     ecx, edi
0x180018eb0  sub     ecx, 1
0x180018eb3  jz      short loc_180018EBA
0x180018eb5  cmp     ecx, 1
0x180018eb8  jnz     short loc_180018ED3
0x180018eba  mov     qword ptr [rbx+0D8h], 0
0x180018ec5  mov     edx, 5
0x180018eca  mov     rcx, rbx
0x180018ecd  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x180018ed2  nop
0x180018ed3  lea     rcx, [rsp+88h+var_40]; this
0x180018ed8  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x180018edd  nop
0x180018ede  jmp     short loc_180018EF4
0x180018ee0  mov     rbx, [rsp+88h+arg_0]
0x180018ee8  mov     rsi, [rsp+88h+arg_8]
0x180018ef0  mov     edi, [rsp+88h+var_58]
0x180018ef4  cmp     edi, 3
0x180018ef7  jz      short loc_180018F4F
0x180018ef9  xor     r8d, r8d; struct CReader::ActiveState *
0x180018efc  mov     rdx, rbx; struct CReader *
0x180018eff  lea     rcx, [rsp+88h+var_40]; this
0x180018f04  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x180018f09  nop
0x180018f0a  mov     rcx, rbx; this
0x180018f0d  call    ?VerifyState@CReader@@QEAAXXZ; CReader::VerifyState(void)
0x180018f12  mov     rdx, rsi; struct CReader::ActiveState *
0x180018f15  mov     rcx, rbx; this
0x180018f18  call    ?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::VerifyActive(CReader::ActiveState const *)
0x180018f1d  mov     edx, [rsp+88h+arg_10]; unsigned int
0x180018f24  mov     rcx, rbx; this
0x180018f27  call    ?Dispose@CReader@@IEAAXK@Z; CReader::Dispose(ulong)
0x180018f2c  mov     rax, [rsp+88h+arg_18]
0x180018f34  mov     dword ptr [rax], 0
0x180018f3a  lea     rcx, [rsp+88h+var_40]; this
0x180018f3f  call    ??1CLatchReader@@QEAA@XZ; CLatchReader::~CLatchReader(void)
0x180018f44  nop
0x180018f45  jmp     short loc_180018F4F
0x180018f47  mov     rbx, [rsp+88h+arg_0]
0x180018f4f  mov     rcx, rbx; this
0x180018f52  call    ?PowerDownTimeoutStart@CReader@@IEAAXXZ; CReader::PowerDownTimeoutStart(void)
0x180018f57  mov     rdi, [rsp+88h+var_30]
0x180018f5c  lea     rcx, [rdi+0F0h]; this
0x180018f63  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x180018f68  test    eax, eax
0x180018f6a  jnz     short loc_180018F5C
0x180018f6c  mov     rcx, rbx; this
0x180018f6f  add     rsp, 70h
0x180018f73  pop     rdi
0x180018f74  pop     rsi
0x180018f75  pop     rbx
0x180018f76  jmp     ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
```
