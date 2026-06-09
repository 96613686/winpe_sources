# HyperVStorage::GetVariantValue(ushort const *,tagVARIANT &)

- ea: `0x1401c8da0`
- end: `0x1401c905c`
- name: `?GetVariantValue@HyperVStorage@@QEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(HyperVStorage *this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1401ea580`

## callees

- `0x140036d94`
- `0x140039d48`
- `0x14003a5e0`
- `0x1400b9ba4`
- `0x1400f55ec`
- `0x140132940`
- `0x1401335fc`
- `0x1401c8da0`
- `0x1401d55d4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401c8df1`
- `OLEAUT32!__imp_VariantInit` at `0x1401c8df1`
- `OLEAUT32!__imp_VariantClear` at `0x1401c9027`
- `OLEAUT32!__imp_VariantClear` at `0x1401c9027`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401c8f16`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401c8f16`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401c9014`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401c9014`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401c8f46`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401c8f46`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401c8ee4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401c8ee4`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall HyperVStorage::GetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  HyperVStorageKeyTableEntry *v7; // r13
  unsigned int v8; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  HyperVStorageKeyTableEntry *v10; // rcx
  ULONG ValueSizeInBytes; // eax
  SAFEARRAY *Vector; // rcx
  HyperVStorageKeyTableEntry *v13; // rcx
  UINT FileObjectDataSizeInBytes; // eax
  BSTR v15; // rax
  unsigned int v16; // r9d
  int v17; // edi
  __int16 v18; // ax
  __int64 v19; // [rsp+28h] [rbp-80h]
  UINT v20; // [rsp+40h] [rbp-68h] BYREF
  __int64 v21; // [rsp+48h] [rbp-60h] BYREF
  struct HyperVStorageServices *v22; // [rsp+50h] [rbp-58h]
  struct tagVARIANT *v23; // [rsp+58h] [rbp-50h]
  struct tagVARIANT *v24; // [rsp+60h] [rbp-48h]
  void *ppvData; // [rsp+68h] [rbp-40h] BYREF
  int v26; // [rsp+70h] [rbp-38h] BYREF

  v22 = this;
  v24 = a3;
  v23 = a3;
  if ( !a2 )
    HvsThrowHResultError(-2147024809);
  VariantInit(a3);
  v21 = 0;
  if ( !(unsigned int)HyperVStorage::GetOrCreateNode(this, a2, 0, (__int64)&v21, 0, v19, 0) )
    return 2147942402LL;
  v26 = 0;
  ppvData = 0;
  v7 = *(HyperVStorageKeyTableEntry **)(v21 + 40);
  LODWORD(v21) = **(unsigned __int8 **)v7;
  switch ( (_DWORD)v21 )
  {
    case 3:
      a3->vt = 20;
      break;
    case 4:
      a3->vt = 21;
      break;
    case 5:
      a3->vt = 5;
      break;
    default:
      switch ( (_DWORD)v21 )
      {
        case 6:
          if ( (unsigned int)HyperVStorageKeyTableEntry::PointsToFileObject(v7) )
            FileObjectDataSizeInBytes = (unsigned int)HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v13);
          else
            FileObjectDataSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v13);
          v8 = FileObjectDataSizeInBytes;
          v20 = FileObjectDataSizeInBytes;
          v15 = SysAllocStringByteLen(0, FileObjectDataSizeInBytes);
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          a3->llVal = (LONGLONG)v15;
          ppvData = v15;
          memset_0(v15, 0, v8 + 2LL);
          a3->vt = 8;
          break;
        case 7:
          if ( (unsigned int)HyperVStorageKeyTableEntry::PointsToFileObject(v7) )
            ValueSizeInBytes = (unsigned int)HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v10);
          else
            ValueSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v10);
          v8 = ValueSizeInBytes;
          v20 = ValueSizeInBytes;
          Vector = SafeArrayCreateVector(0x11u, 0, ValueSizeInBytes);
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          a3->llVal = (LONGLONG)Vector;
          if ( !Vector )
            HvsThrowHResultError(-2147024882);
          a3->vt = 8209;
          SafeArrayAccessData(Vector, &ppvData);
          break;
        case 8:
          ppvData = &v26;
          v8 = 4;
          v20 = 4;
          a3->vt = 11;
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          break;
        default:
          HvsThrowHResultError(-2147024809);
      }
      goto LABEL_27;
  }
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
  ppvData = &a3->decVal.8;
  v8 = 8;
  v20 = 8;
LABEL_27:
  v16 = v8;
  v17 = v21;
  HyperVStorage::GetValueInternal(v22, v7, v21, v16, (unsigned __int8 *)ppvData, &v20);
  if ( v17 == 8 )
  {
    if ( v26 )
      v18 = -1;
    else
      v18 = 0;
    p_llVal->iVal = v18;
  }
  if ( a3->vt == 8209 )
    SafeArrayUnaccessData(p_llVal->parray);
  return 0;
}

```

## disassembly

```asm
0x1401c8da0  mov     [rsp+arg_18], rsi
0x1401c8da5  push    rdi
0x1401c8da6  push    r12
0x1401c8da8  push    r13
0x1401c8daa  push    r14
0x1401c8dac  push    r15
0x1401c8dae  sub     rsp, 80h
0x1401c8db5  mov     rax, cs:__security_cookie
0x1401c8dbc  xor     rax, rsp
0x1401c8dbf  mov     [rsp+0A8h+var_30], rax
0x1401c8dc4  mov     r12, r8
0x1401c8dc7  mov     rdi, rdx
0x1401c8dca  mov     rsi, rcx
0x1401c8dcd  mov     [rsp+0A8h+var_58], rcx
0x1401c8dd2  mov     [rsp+0A8h+var_48], r8
0x1401c8dd7  mov     r14, r8
0x1401c8dda  mov     [rsp+0A8h+var_50], r8
0x1401c8ddf  test    rdx, rdx
0x1401c8de2  jnz     short loc_1401C8DEE
0x1401c8de4  mov     ecx, 80070057h; int
0x1401c8de9  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8dee  mov     rcx, r12; pvarg
0x1401c8df1  call    cs:__imp_VariantInit
0x1401c8df8  nop     dword ptr [rax+rax+00h]
0x1401c8dfd  mov     [rsp+0A8h+var_60], 0
0x1401c8e06  mov     [rsp+0A8h+var_78], 0
0x1401c8e0b  mov     [rsp+0A8h+var_88], 0
0x1401c8e14  lea     r9, [rsp+0A8h+var_60]
0x1401c8e19  xor     r8d, r8d
0x1401c8e1c  mov     rdx, rdi
0x1401c8e1f  mov     rcx, rsi
0x1401c8e22  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x1401c8e27  test    eax, eax
0x1401c8e29  jnz     short loc_1401C8E35
0x1401c8e2b  mov     eax, 80070002h
0x1401c8e30  jmp     loc_1401C9035
0x1401c8e35  mov     [rsp+0A8h+var_38], 0
0x1401c8e3d  mov     [rsp+0A8h+ppvData], 0
0x1401c8e46  mov     rax, [rsp+0A8h+var_60]
0x1401c8e4b  mov     r13, [rax+28h]
0x1401c8e4f  mov     rax, [r13+0]
0x1401c8e53  movzx   ecx, byte ptr [rax]
0x1401c8e56  mov     dword ptr [rsp+0A8h+var_60], ecx
0x1401c8e5a  sub     ecx, 3
0x1401c8e5d  jz      loc_1401C8F8F
0x1401c8e63  sub     ecx, 1
0x1401c8e66  jz      loc_1401C8F86
0x1401c8e6c  sub     ecx, 1
0x1401c8e6f  jz      loc_1401C8F7D
0x1401c8e75  sub     ecx, 1
0x1401c8e78  jz      loc_1401C8F24
0x1401c8e7e  sub     ecx, 1
0x1401c8e81  jz      short loc_1401C8EBC
0x1401c8e83  cmp     ecx, 1
0x1401c8e86  jz      short loc_1401C8E92
0x1401c8e88  mov     ecx, 80070057h; int
0x1401c8e8d  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8e92  lea     rax, [rsp+0A8h+var_38]
0x1401c8e97  mov     [rsp+0A8h+ppvData], rax
0x1401c8e9c  mov     edi, 4
0x1401c8ea1  mov     [rsp+0A8h+var_68], edi
0x1401c8ea5  mov     word ptr [r12], 0Bh
0x1401c8eac  lea     rsi, [r12+8]
0x1401c8eb1  mov     r15d, 8
0x1401c8eb7  jmp     loc_1401C8FAE
0x1401c8ebc  mov     rcx, r13; this
0x1401c8ebf  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401c8ec4  test    eax, eax
0x1401c8ec6  jnz     short loc_1401C8ECF
0x1401c8ec8  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401c8ecd  jmp     short loc_1401C8ED4
0x1401c8ecf  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401c8ed4  mov     edi, eax
0x1401c8ed6  mov     [rsp+0A8h+var_68], eax
0x1401c8eda  mov     ecx, 11h; vt
0x1401c8edf  mov     r8d, eax; cElements
0x1401c8ee2  xor     edx, edx; lLbound
0x1401c8ee4  call    cs:__imp_SafeArrayCreateVector
0x1401c8eeb  nop     dword ptr [rax+rax+00h]
0x1401c8ef0  mov     rcx, rax; psa
0x1401c8ef3  lea     rsi, [r12+8]
0x1401c8ef8  mov     [rsi], rax
0x1401c8efb  test    rax, rax
0x1401c8efe  jnz     short loc_1401C8F0A
0x1401c8f00  mov     ecx, 8007000Eh; int
0x1401c8f05  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8f0a  mov     word ptr [r12], 2011h
0x1401c8f11  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401c8f16  call    cs:__imp_SafeArrayAccessData
0x1401c8f1d  nop     dword ptr [rax+rax+00h]
0x1401c8f22  jmp     short loc_1401C8EB1
0x1401c8f24  mov     rcx, r13; this
0x1401c8f27  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401c8f2c  test    eax, eax
0x1401c8f2e  jnz     short loc_1401C8F37
0x1401c8f30  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401c8f35  jmp     short loc_1401C8F3C
0x1401c8f37  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401c8f3c  mov     edi, eax
0x1401c8f3e  mov     [rsp+0A8h+var_68], eax
0x1401c8f42  mov     edx, eax; len
0x1401c8f44  xor     ecx, ecx; psz
0x1401c8f46  call    cs:__imp_SysAllocStringByteLen
0x1401c8f4d  nop     dword ptr [rax+rax+00h]
0x1401c8f52  lea     rsi, [r12+8]
0x1401c8f57  mov     [rsi], rax
0x1401c8f5a  mov     [rsp+0A8h+ppvData], rax
0x1401c8f5f  mov     r8d, edi
0x1401c8f62  add     r8, 2; Size
0x1401c8f66  xor     edx, edx; Val
0x1401c8f68  mov     rcx, rax; void *
0x1401c8f6b  call    memset_0
0x1401c8f70  mov     r15d, 8
0x1401c8f76  mov     [r12], r15w
0x1401c8f7b  jmp     short loc_1401C8FAE
0x1401c8f7d  mov     word ptr [r12], 5
0x1401c8f84  jmp     short loc_1401C8F96
0x1401c8f86  mov     word ptr [r12], 15h
0x1401c8f8d  jmp     short loc_1401C8F96
0x1401c8f8f  mov     word ptr [r12], 14h
0x1401c8f96  lea     rsi, [r12+8]
0x1401c8f9b  mov     r15d, 8
0x1401c8fa1  mov     [rsp+0A8h+ppvData], rsi
0x1401c8fa6  mov     edi, r15d
0x1401c8fa9  mov     [rsp+0A8h+var_68], r15d
0x1401c8fae  lea     rax, [rsp+0A8h+var_68]
0x1401c8fb3  mov     [rsp+0A8h+var_80], rax
0x1401c8fb8  mov     rax, [rsp+0A8h+ppvData]
0x1401c8fbd  mov     [rsp+0A8h+var_88], rax
0x1401c8fc2  mov     r9d, edi
0x1401c8fc5  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401c8fc9  mov     r8d, edi
0x1401c8fcc  mov     rdx, r13
0x1401c8fcf  mov     rcx, [rsp+0A8h+var_58]
0x1401c8fd4  call    ?GetValueInternal@HyperVStorage@@IEBAXPEBVHyperVStorageKeyTableEntry@@W4HyperVStorageKeyType@@IPEAEAEAI@Z; HyperVStorage::GetValueInternal(HyperVStorageKeyTableEntry const *,HyperVStorageKeyType,uint,uchar *,uint &)
0x1401c8fd9  cmp     edi, r15d
0x1401c8fdc  jnz     short loc_1401C8FEF
0x1401c8fde  cmp     [rsp+0A8h+var_38], 0
0x1401c8fe3  jz      short loc_1401C8FEA
0x1401c8fe5  or      eax, 0FFFFFFFFh
0x1401c8fe8  jmp     short loc_1401C8FEC
0x1401c8fea  xor     eax, eax
0x1401c8fec  mov     [rsi], ax
0x1401c8fef  xor     edi, edi
0x1401c8ff1  jmp     short loc_1401C9005
0x1401c8ff3  mov     r14, [rsp+0A8h+var_50]
0x1401c8ff8  lea     rsi, [r14+8]
0x1401c8ffc  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401c9000  mov     r12, [rsp+0A8h+var_48]
0x1401c9005  mov     eax, 2011h
0x1401c900a  cmp     [r12], ax
0x1401c900f  jnz     short loc_1401C9020
0x1401c9011  mov     rcx, [rsi]; psa
0x1401c9014  call    cs:__imp_SafeArrayUnaccessData
0x1401c901b  nop     dword ptr [rax+rax+00h]
0x1401c9020  test    edi, edi
0x1401c9022  jns     short loc_1401C9033
0x1401c9024  mov     rcx, r14; pvarg
0x1401c9027  call    cs:__imp_VariantClear
0x1401c902e  nop     dword ptr [rax+rax+00h]
0x1401c9033  mov     eax, edi
0x1401c9035  mov     rcx, [rsp+0A8h+var_30]
0x1401c903a  xor     rcx, rsp; StackCookie
0x1401c903d  call    __security_check_cookie
0x1401c9042  mov     rsi, [rsp+0A8h+arg_18]
0x1401c904a  add     rsp, 80h
0x1401c9051  pop     r15
0x1401c9053  pop     r14
0x1401c9055  pop     r13
0x1401c9057  pop     r12
0x1401c9059  pop     rdi
0x1401c905a  retn
```
