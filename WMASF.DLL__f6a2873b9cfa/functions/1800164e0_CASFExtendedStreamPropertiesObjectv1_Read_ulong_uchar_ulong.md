# CASFExtendedStreamPropertiesObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x1800164e0`
- end: `0x1800166a6`
- name: `?Read@CASFExtendedStreamPropertiesObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `454`
- prototype: `int(CASFExtendedStreamPropertiesObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x1800164e0`
- `0x180016704`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFExtendedStreamPropertiesObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  unsigned __int16 v10; // r12
  unsigned __int16 v11; // ax
  __int64 v12; // r10
  __int64 v13; // rdx
  int v14; // eax
  struct IWMSCriticalSection *v15; // rcx
  unsigned __int16 v17; // [rsp+30h] [rbp-30h]
  unsigned int v18; // [rsp+34h] [rbp-2Ch] BYREF
  char v19[8]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h]
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v19, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_20:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return v8;
  }
  if ( !a4 )
    goto LABEL_21;
  if ( !a2 )
  {
LABEL_19:
    *a4 = 26;
    v8 = -1072887855;
    goto LABEL_20;
  }
  if ( !a3 )
  {
LABEL_21:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
    return 2147942487LL;
  }
  if ( a2 < 0x1A )
    goto LABEL_19;
  v9 = *(_OWORD *)a3;
  v18 = 26;
  v10 = 0;
  v8 = -1072887855;
  *((_OWORD *)this + 3) = v9;
  this[8] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  v11 = *((_WORD *)a3 + 12);
  v17 = v11;
  while ( v10 < v11 )
  {
    v21 = 0;
    if ( (unsigned int)CHECK_FOR_SPACE(&v18, 6u, a2) == -1072887855 )
    {
      *a4 = v18;
      goto LABEL_20;
    }
    v13 = *((unsigned int *)this + 76);
    LOWORD(v21) = *(_WORD *)v12;
    v14 = *(_DWORD *)(v12 + 2);
    v20 = v12 + 6;
    HIDWORD(v21) = v14;
    if ( (int)CTSparseBlock<unsigned long,CASFExtendedStreamPropertiesObjectv1::EXTENDED_STREAM_PROPS_RECORD,20,0>::SetValue(
                this + 11,
                v13,
                v21) >= 0 )
      ++*((_DWORD *)this + 76);
    v11 = v17;
    ++v10;
  }
  *a4 = v18;
  v15 = this[5];
  if ( v15 )
  {
    v21 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v15)(
           v15,
           &IID_IASFReadWriteTracker,
           &v21) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v21 + 72LL))(
        v21,
        a3,
        *a4,
        (char *)this + 48);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
  return 0;
}

```

## disassembly

```asm
0x1800164e0  mov     [rsp-38h+arg_8], rbx
0x1800164e5  push    rbp
0x1800164e6  push    rsi
0x1800164e7  push    rdi
0x1800164e8  push    r12
0x1800164ea  push    r13
0x1800164ec  push    r14
0x1800164ee  push    r15
0x1800164f0  mov     rbp, rsp
0x1800164f3  sub     rsp, 60h
0x1800164f7  mov     rax, cs:__security_cookie
0x1800164fe  xor     rax, rsp
0x180016501  mov     [rbp+var_10], rax
0x180016505  mov     r15d, edx
0x180016508  mov     rsi, rcx
0x18001650b  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001650f  mov     rdi, r9
0x180016512  lea     rcx, [rbp+var_28]; this
0x180016516  mov     r14, r8
0x180016519  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001651e  cmp     qword ptr [rsi+28h], 0
0x180016523  jnz     short loc_18001652F
0x180016525  mov     ebx, 0C00D07F6h
0x18001652a  jmp     loc_180016667
0x18001652f  test    rdi, rdi
0x180016532  jz      loc_180016674
0x180016538  mov     ecx, 1Ah
0x18001653d  test    r15d, r15d
0x180016540  jz      loc_180016660
0x180016546  test    r14, r14
0x180016549  jz      loc_180016674
0x18001654f  cmp     r15d, ecx
0x180016552  jb      loc_180016660
0x180016558  movups  xmm0, xmmword ptr [r14]
0x18001655c  lea     r10, [r14+1Ah]
0x180016560  mov     [rbp+var_2C], ecx
0x180016563  xor     r12d, r12d
0x180016566  mov     ebx, 0C00D07D1h
0x18001656b  movdqu  xmmword ptr [rsi+30h], xmm0
0x180016570  mov     rax, [r14+10h]
0x180016574  mov     [rsi+40h], rax
0x180016578  movzx   eax, word ptr [r14+18h]
0x18001657d  mov     [rbp+var_30], ax
0x180016581  cmp     r12w, ax
0x180016585  jnb     short loc_1800165F4
0x180016587  mov     r8d, r15d; unsigned int
0x18001658a  mov     [rbp+var_18], 0
0x180016592  mov     edx, 6; unsigned int
0x180016597  lea     rcx, [rbp+var_2C]; unsigned int *
0x18001659b  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x1800165a0  cmp     eax, ebx
0x1800165a2  jz      short loc_1800165ED
0x1800165a4  movzx   eax, word ptr [r10]
0x1800165a8  lea     rcx, [r10+2]
0x1800165ac  mov     edx, [rsi+130h]
0x1800165b2  mov     word ptr [rbp+var_18], ax
0x1800165b6  mov     eax, [rcx]
0x1800165b8  add     rcx, 4
0x1800165bc  mov     [rbp+var_20], rcx
0x1800165c0  lea     rcx, [rsi+58h]
0x1800165c4  mov     dword ptr [rbp+var_18+4], eax
0x1800165c7  mov     r8, [rbp+var_18]
0x1800165cb  call    ?SetValue@?$CTSparseBlock@KUEXTENDED_STREAM_PROPS_RECORD@CASFExtendedStreamPropertiesObjectv1@@$0BE@$0A@@@QEAAJKUEXTENDED_STREAM_PROPS_RECORD@CASFExtendedStreamPropertiesObjectv1@@@Z; CTSparseBlock<ulong,CASFExtendedStreamPropertiesObjectv1::EXTENDED_STREAM_PROPS_RECORD,20,0>::SetValue(ulong,CASFExtendedStreamPropertiesObjectv1::EXTENDED_STREAM_PROPS_RECORD)
0x1800165d0  mov     ecx, 1
0x1800165d5  test    eax, eax
0x1800165d7  js      short loc_1800165DF
0x1800165d9  add     [rsi+130h], ecx
0x1800165df  movzx   eax, [rbp+var_30]
0x1800165e3  add     r12w, cx
0x1800165e7  mov     r10, [rbp+var_20]
0x1800165eb  jmp     short loc_180016581
0x1800165ed  mov     eax, [rbp+var_2C]
0x1800165f0  mov     [rdi], eax
0x1800165f2  jmp     short loc_180016667
0x1800165f4  mov     eax, [rbp+var_2C]
0x1800165f7  mov     [rdi], eax
0x1800165f9  mov     rcx, [rsi+28h]
0x1800165fd  test    rcx, rcx
0x180016600  jz      short loc_180016653
0x180016602  mov     [rbp+var_18], 0
0x18001660a  lea     r8, [rbp+var_18]
0x18001660e  mov     rax, [rcx]
0x180016611  lea     rdx, IID_IASFReadWriteTracker
0x180016618  mov     rax, [rax]
0x18001661b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016620  test    eax, eax
0x180016622  js      short loc_180016653
0x180016624  mov     rcx, [rbp+var_18]
0x180016628  lea     r9, [rsi+30h]
0x18001662c  mov     r8d, [rdi]
0x18001662f  mov     rdx, r14
0x180016632  mov     rax, [rcx]
0x180016635  mov     rax, [rax+48h]
0x180016639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001663e  mov     rcx, [rbp+var_18]
0x180016642  test    rcx, rcx
0x180016645  jz      short loc_180016653
0x180016647  mov     rax, [rcx]
0x18001664a  mov     rax, [rax+10h]
0x18001664e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016653  lea     rcx, [rbp+var_28]; this
0x180016657  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001665c  xor     eax, eax
0x18001665e  jmp     short loc_180016682
0x180016660  mov     [rdi], ecx
0x180016662  mov     ebx, 0C00D07D1h
0x180016667  lea     rcx, [rbp+var_28]; this
0x18001666b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180016670  mov     eax, ebx
0x180016672  jmp     short loc_180016682
0x180016674  lea     rcx, [rbp+var_28]; this
0x180016678  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001667d  mov     eax, 80070057h
0x180016682  mov     rcx, [rbp+var_10]
0x180016686  xor     rcx, rsp; StackCookie
0x180016689  call    __security_check_cookie
0x18001668e  mov     rbx, [rsp+60h+arg_8]
0x180016696  add     rsp, 60h
0x18001669a  pop     r15
0x18001669c  pop     r14
0x18001669e  pop     r13
0x1800166a0  pop     r12
0x1800166a2  pop     rdi
0x1800166a3  pop     rsi
0x1800166a4  pop     rbp
0x1800166a5  retn
```
