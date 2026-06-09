# CASFContentEncryptionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180019090`
- end: `0x18001939a`
- name: `?Read@CASFContentEncryptionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x180019090`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentEncryptionObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  struct IWMSCriticalSection *v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // edx
  unsigned int v13; // edx
  struct IWMSCriticalSection *v14; // rax
  unsigned int v15; // r8d
  unsigned int *v16; // r10
  __int64 v17; // r15
  unsigned int *v18; // r12
  struct IWMSCriticalSection *v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // r8d
  __int64 v22; // r15
  unsigned int *v23; // r12
  struct IWMSCriticalSection *v24; // rax
  unsigned int v25; // r8d
  size_t v26; // r15
  struct IWMSCriticalSection *v27; // rax
  struct IWMSCriticalSection *v28; // rcx
  GUID *v29; // rbx
  char v31[8]; // [rsp+30h] [rbp-20h] BYREF
  GUID *v32; // [rsp+38h] [rbp-18h]
  unsigned int v33[2]; // [rsp+40h] [rbp-10h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v31, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_38:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
    return v8;
  }
  if ( !a4 )
    goto LABEL_39;
  if ( !(_DWORD)v4 )
  {
LABEL_37:
    *a4 = 40;
    v8 = -1072887855;
    goto LABEL_38;
  }
  if ( !a3 )
  {
LABEL_39:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x28 )
    goto LABEL_37;
  v9 = *(_OWORD *)a3;
  v8 = -1072887855;
  v32 = (GUID *)(this + 6);
  *((_OWORD *)this + 3) = v9;
  v10 = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  this[8] = v10;
  if ( v4 < (unsigned __int64)v10 )
  {
    v11 = (unsigned int)v10;
LABEL_9:
    *a4 = v11;
    goto LABEL_38;
  }
  v12 = *((_DWORD *)a3 + 6);
  *((_DWORD *)this + 28) = v12;
  v33[0] = 28;
  if ( v12 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v33, v12, v4) == -1072887855 )
      goto LABEL_36;
    v14 = (struct IWMSCriticalSection *)operator new[](v13);
    this[13] = v14;
    if ( !v14 )
      goto LABEL_28;
    memcpy_0(v14, a3 + 28, *((unsigned int *)this + 28));
  }
  if ( (unsigned int)CHECK_FOR_SPACE(v33, 4u, v4) == -1072887855 )
    goto LABEL_36;
  v17 = *v16;
  v18 = v16 + 1;
  if ( (_DWORD)v17 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v33, v17, v15) == -1072887855 )
      goto LABEL_36;
    v19 = (struct IWMSCriticalSection *)operator new[]((unsigned int)v17);
    this[11] = v19;
    if ( !v19 )
      goto LABEL_28;
    memcpy_0(v19, v18, (unsigned int)v17);
    v18 = (unsigned int *)((char *)v18 + v17);
    *((_BYTE *)this[11] + (unsigned int)(v17 - 1)) = 0;
  }
  if ( (unsigned int)CHECK_FOR_SPACE(v33, 4u, v4) == -1072887855 )
    goto LABEL_36;
  v22 = *v18;
  v23 = (unsigned int *)((char *)v18 + v20);
  if ( (_DWORD)v22 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v33, v22, v21) == -1072887855 )
      goto LABEL_36;
    v24 = (struct IWMSCriticalSection *)operator new[]((unsigned int)v22);
    this[12] = v24;
    if ( v24 )
    {
      memcpy_0(v24, v23, (unsigned int)v22);
      v23 = (unsigned int *)((char *)v23 + v22);
      *((_BYTE *)this[12] + (unsigned int)(v22 - 1)) = 0;
      goto LABEL_24;
    }
LABEL_28:
    v8 = -2147024882;
    goto LABEL_38;
  }
LABEL_24:
  if ( (unsigned int)CHECK_FOR_SPACE(v33, 4u, v4) == -1072887855 )
    goto LABEL_36;
  v26 = *v23;
  if ( (_DWORD)v26 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v33, v26, v25) != -1072887855 )
    {
      v27 = (struct IWMSCriticalSection *)operator new[]((unsigned int)v26);
      this[15] = v27;
      if ( !v27 )
        goto LABEL_28;
      memcpy_0(v27, v23 + 1, v26);
      *((_BYTE *)this[15] + (unsigned int)(v26 - 1)) = 0;
      goto LABEL_30;
    }
LABEL_36:
    v11 = v33[0];
    goto LABEL_9;
  }
LABEL_30:
  *a4 = v33[0];
  v28 = this[5];
  if ( v28
    && (*(_QWORD *)v33 = 0,
        (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, unsigned int *))v28)(
          v28,
          &IID_IASFReadWriteTracker,
          v33) >= 0) )
  {
    v29 = (GUID *)(this + 6);
    (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v33 + 72LL))(
      *(_QWORD *)v33,
      a3,
      *a4,
      (char *)this + 48);
    if ( *(_QWORD *)v33 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
  }
  else
  {
    v29 = v32;
  }
  *v29 = CLSID_ASFContentEncryptionObjectv1;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
  return 0;
}

```

## disassembly

```asm
0x180019090  mov     [rsp-38h+arg_8], rbx
0x180019095  push    rbp
0x180019096  push    rsi
0x180019097  push    rdi
0x180019098  push    r12
0x18001909a  push    r13
0x18001909c  push    r14
0x18001909e  push    r15
0x1800190a0  mov     rbp, rsp
0x1800190a3  sub     rsp, 50h
0x1800190a7  mov     rax, cs:__security_cookie
0x1800190ae  xor     rax, rsp
0x1800190b1  mov     [rbp+var_8], rax
0x1800190b5  mov     esi, edx
0x1800190b7  mov     rdi, rcx
0x1800190ba  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800190be  mov     r14, r9
0x1800190c1  lea     rcx, [rbp+var_20]; this
0x1800190c5  mov     r13, r8
0x1800190c8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800190cd  cmp     qword ptr [rdi+28h], 0
0x1800190d2  jnz     short loc_1800190DE
0x1800190d4  mov     ebx, 0C00D07F6h
0x1800190d9  jmp     loc_18001935B
0x1800190de  test    r14, r14
0x1800190e1  jz      loc_180019368
0x1800190e7  test    esi, esi
0x1800190e9  jz      loc_18001934F
0x1800190ef  test    r13, r13
0x1800190f2  jz      loc_180019368
0x1800190f8  cmp     esi, 28h ; '('
0x1800190fb  jb      loc_18001934F
0x180019101  movups  xmm0, xmmword ptr [r13+0]
0x180019106  lea     rax, [rdi+30h]
0x18001910a  mov     ebx, 0C00D07D1h
0x18001910f  mov     [rbp+var_18], rax
0x180019113  movdqu  xmmword ptr [rax], xmm0
0x180019117  mov     rcx, [r13+10h]
0x18001911b  mov     [rdi+40h], rcx
0x18001911f  cmp     rsi, rcx
0x180019122  jnb     short loc_18001912E
0x180019124  mov     eax, ecx
0x180019126  mov     [r14], eax
0x180019129  jmp     loc_18001935B
0x18001912e  mov     edx, [r13+18h]; unsigned int
0x180019132  lea     r15, [r13+1Ch]
0x180019136  mov     [rdi+70h], edx
0x180019139  mov     [rbp+var_10], 1Ch
0x180019140  test    edx, edx
0x180019142  jz      short loc_180019184
0x180019144  mov     r8d, esi; unsigned int
0x180019147  lea     rcx, [rbp+var_10]; unsigned int *
0x18001914b  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180019150  cmp     eax, ebx
0x180019152  jz      loc_180019347
0x180019158  mov     ecx, edx; unsigned __int64
0x18001915a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001915f  mov     [rdi+68h], rax
0x180019163  test    rax, rax
0x180019166  jz      loc_1800192A0
0x18001916c  mov     r8d, [rdi+70h]; Size
0x180019170  mov     rdx, r15; Src
0x180019173  mov     rcx, rax; void *
0x180019176  call    memcpy_0
0x18001917b  mov     r10d, [rdi+70h]
0x18001917f  add     r10, r15
0x180019182  jmp     short loc_180019187
0x180019184  mov     r10, r15
0x180019187  mov     r8d, esi; unsigned int
0x18001918a  lea     rcx, [rbp+var_10]; unsigned int *
0x18001918e  mov     edx, 4; unsigned int
0x180019193  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180019198  cmp     eax, ebx
0x18001919a  jz      loc_180019347
0x1800191a0  mov     r15d, [r10]
0x1800191a3  lea     r12, [r10+4]
0x1800191a7  test    r15d, r15d
0x1800191aa  jz      short loc_1800191F2
0x1800191ac  mov     edx, r15d; unsigned int
0x1800191af  lea     rcx, [rbp+var_10]; unsigned int *
0x1800191b3  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x1800191b8  cmp     eax, ebx
0x1800191ba  jz      loc_180019347
0x1800191c0  mov     ecx, r15d; unsigned __int64
0x1800191c3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800191c8  mov     [rdi+58h], rax
0x1800191cc  test    rax, rax
0x1800191cf  jz      loc_1800192A0
0x1800191d5  mov     r8d, r15d; Size
0x1800191d8  mov     rdx, r12; Src
0x1800191db  mov     rcx, rax; void *
0x1800191de  call    memcpy_0
0x1800191e3  mov     rax, [rdi+58h]
0x1800191e7  lea     ecx, [r15-1]
0x1800191eb  add     r12, r15
0x1800191ee  mov     byte ptr [rcx+rax], 0
0x1800191f2  mov     r8d, esi; unsigned int
0x1800191f5  lea     rcx, [rbp+var_10]; unsigned int *
0x1800191f9  mov     edx, 4; unsigned int
0x1800191fe  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180019203  cmp     eax, ebx
0x180019205  jz      loc_180019347
0x18001920b  mov     r15d, [r12]
0x18001920f  add     r12, rdx
0x180019212  test    r15d, r15d
0x180019215  jz      short loc_180019259
0x180019217  mov     edx, r15d; unsigned int
0x18001921a  lea     rcx, [rbp+var_10]; unsigned int *
0x18001921e  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180019223  cmp     eax, ebx
0x180019225  jz      loc_180019347
0x18001922b  mov     ecx, r15d; unsigned __int64
0x18001922e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019233  mov     [rdi+60h], rax
0x180019237  test    rax, rax
0x18001923a  jz      short loc_1800192A0
0x18001923c  mov     r8d, r15d; Size
0x18001923f  mov     rdx, r12; Src
0x180019242  mov     rcx, rax; void *
0x180019245  call    memcpy_0
0x18001924a  mov     rax, [rdi+60h]
0x18001924e  lea     ecx, [r15-1]
0x180019252  add     r12, r15
0x180019255  mov     byte ptr [rcx+rax], 0
0x180019259  mov     r8d, esi; unsigned int
0x18001925c  lea     rcx, [rbp+var_10]; unsigned int *
0x180019260  mov     edx, 4; unsigned int
0x180019265  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001926a  cmp     eax, ebx
0x18001926c  jz      loc_180019347
0x180019272  mov     r15d, [r12]
0x180019276  test    r15d, r15d
0x180019279  jz      short loc_1800192C6
0x18001927b  mov     edx, r15d; unsigned int
0x18001927e  lea     rcx, [rbp+var_10]; unsigned int *
0x180019282  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180019287  cmp     eax, ebx
0x180019289  jz      loc_180019347
0x18001928f  mov     ecx, r15d; unsigned __int64
0x180019292  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019297  mov     [rdi+78h], rax
0x18001929b  test    rax, rax
0x18001929e  jnz     short loc_1800192AA
0x1800192a0  mov     ebx, 8007000Eh
0x1800192a5  jmp     loc_18001935B
0x1800192aa  lea     rdx, [r12+4]; Src
0x1800192af  mov     r8, r15; Size
0x1800192b2  mov     rcx, rax; void *
0x1800192b5  call    memcpy_0
0x1800192ba  mov     rax, [rdi+78h]
0x1800192be  lea     ecx, [r15-1]
0x1800192c2  mov     byte ptr [rcx+rax], 0
0x1800192c6  mov     eax, [rbp+var_10]
0x1800192c9  mov     [r14], eax
0x1800192cc  mov     rcx, [rdi+28h]
0x1800192d0  test    rcx, rcx
0x1800192d3  jz      short loc_18001932B
0x1800192d5  mov     qword ptr [rbp+var_10], 0
0x1800192dd  lea     r8, [rbp+var_10]
0x1800192e1  mov     rax, [rcx]
0x1800192e4  lea     rdx, IID_IASFReadWriteTracker
0x1800192eb  mov     rax, [rax]
0x1800192ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f3  test    eax, eax
0x1800192f5  js      short loc_18001932B
0x1800192f7  mov     rcx, qword ptr [rbp+var_10]
0x1800192fb  lea     rbx, [rdi+30h]
0x1800192ff  mov     r8d, [r14]
0x180019302  mov     r9, rbx
0x180019305  mov     rdx, r13
0x180019308  mov     rax, [rcx]
0x18001930b  mov     rax, [rax+48h]
0x18001930f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019314  mov     rcx, qword ptr [rbp+var_10]
0x180019318  test    rcx, rcx
0x18001931b  jz      short loc_18001932F
0x18001931d  mov     rax, [rcx]
0x180019320  mov     rax, [rax+10h]
0x180019324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019329  jmp     short loc_18001932F
0x18001932b  mov     rbx, [rbp+var_18]
0x18001932f  movups  xmm0, xmmword ptr cs:CLSID_ASFContentEncryptionObjectv1.Data1
0x180019336  lea     rcx, [rbp+var_20]; this
0x18001933a  movdqu  xmmword ptr [rbx], xmm0
0x18001933e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019343  xor     eax, eax
0x180019345  jmp     short loc_180019376
0x180019347  mov     eax, [rbp+var_10]
0x18001934a  jmp     loc_180019126
0x18001934f  mov     dword ptr [r14], 28h ; '('
0x180019356  mov     ebx, 0C00D07D1h
0x18001935b  lea     rcx, [rbp+var_20]; this
0x18001935f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019364  mov     eax, ebx
0x180019366  jmp     short loc_180019376
0x180019368  lea     rcx, [rbp+var_20]; this
0x18001936c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019371  mov     eax, 80070057h
0x180019376  mov     rcx, [rbp+var_8]
0x18001937a  xor     rcx, rsp; StackCookie
0x18001937d  call    __security_check_cookie
0x180019382  mov     rbx, [rsp+50h+arg_8]
0x18001938a  add     rsp, 50h
0x18001938e  pop     r15
0x180019390  pop     r14
0x180019392  pop     r13
0x180019394  pop     r12
0x180019396  pop     rdi
0x180019397  pop     rsi
0x180019398  pop     rbp
0x180019399  retn
```
