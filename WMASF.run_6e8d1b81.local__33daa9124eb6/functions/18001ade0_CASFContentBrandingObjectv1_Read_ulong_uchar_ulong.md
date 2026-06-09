# CASFContentBrandingObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18001ade0`
- end: `0x18001b06d`
- name: `?Read@CASFContentBrandingObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18001ade0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentBrandingObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int128 v10; // xmm0
  struct IWMSCriticalSection *v11; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // edx
  struct IWMSCriticalSection *v16; // rax
  unsigned int v17; // r8d
  unsigned int *v18; // r10
  __int64 v19; // r15
  unsigned int *v20; // r12
  struct IWMSCriticalSection *v21; // rax
  unsigned int v22; // r8d
  size_t v23; // r15
  struct IWMSCriticalSection *v24; // rax
  struct IWMSCriticalSection *v25; // rcx
  char v26[8]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v27[2]; // [rsp+38h] [rbp-18h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v26, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_11:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v26);
    return v8;
  }
  if ( !a4 )
    goto LABEL_34;
  v9 = 24;
  if ( !(_DWORD)v4 )
  {
LABEL_9:
    v8 = -1072887855;
LABEL_10:
    *a4 = v9;
    goto LABEL_11;
  }
  if ( !a3 )
  {
LABEL_34:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v26);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_9;
  v10 = *(_OWORD *)a3;
  v27[0] = 24;
  *((_OWORD *)this + 3) = v10;
  v11 = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  this[8] = v11;
  if ( v4 < (unsigned __int64)v11 )
  {
    v9 = (unsigned int)v11;
    goto LABEL_9;
  }
  v8 = -1072887855;
  if ( (unsigned int)CHECK_FOR_SPACE(v27, 8u, v4) == -1072887855 )
    goto LABEL_33;
  *((_DWORD *)this + 21) = *((_DWORD *)a3 + 6);
  v14 = *((_DWORD *)a3 + 7);
  *((_DWORD *)this + 24) = v14;
  if ( v14 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v27, v14, v13) == -1072887855 )
      goto LABEL_33;
    v16 = (struct IWMSCriticalSection *)operator new[](v15);
    this[11] = v16;
    if ( !v16 )
      goto LABEL_26;
    memcpy_0(v16, a3 + 32, *((unsigned int *)this + 24));
  }
  if ( (unsigned int)CHECK_FOR_SPACE(v27, 4u, v4) == -1072887855 )
    goto LABEL_33;
  v19 = *v18;
  v20 = v18 + 1;
  if ( (_DWORD)v19 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v27, v19, v17) == -1072887855 )
      goto LABEL_33;
    v21 = (struct IWMSCriticalSection *)operator new[]((unsigned int)v19);
    this[13] = v21;
    if ( v21 )
    {
      memcpy_0(v21, v20, (unsigned int)v19);
      v20 = (unsigned int *)((char *)v20 + v19);
      *((_BYTE *)this[13] + (unsigned int)(v19 - 1)) = 0;
      goto LABEL_22;
    }
LABEL_26:
    v8 = -2147024882;
    goto LABEL_11;
  }
LABEL_22:
  if ( (unsigned int)CHECK_FOR_SPACE(v27, 4u, v4) == -1072887855 )
    goto LABEL_33;
  v23 = *v20;
  if ( (_DWORD)v23 )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(v27, v23, v22) != -1072887855 )
    {
      v24 = (struct IWMSCriticalSection *)operator new[]((unsigned int)v23);
      this[14] = v24;
      if ( !v24 )
        goto LABEL_26;
      memcpy_0(v24, v20 + 1, v23);
      *((_BYTE *)this[14] + (unsigned int)(v23 - 1)) = 0;
      goto LABEL_28;
    }
LABEL_33:
    v9 = v27[0];
    goto LABEL_10;
  }
LABEL_28:
  *a4 = v27[0];
  v25 = this[5];
  if ( v25 )
  {
    *(_QWORD *)v27 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, unsigned int *))v25)(
           v25,
           &IID_IASFReadWriteTracker,
           v27) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, char *))(**(_QWORD **)v27 + 72LL))(
        *(_QWORD *)v27,
        a3,
        *a4,
        (char *)this + 48);
      if ( *(_QWORD *)v27 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 16LL))(*(_QWORD *)v27);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v26);
  return 0;
}

```

## disassembly

```asm
0x18001ade0  mov     [rsp-38h+arg_8], rbx
0x18001ade5  push    rbp
0x18001ade6  push    rsi
0x18001ade7  push    rdi
0x18001ade8  push    r12
0x18001adea  push    r13
0x18001adec  push    r14
0x18001adee  push    r15
0x18001adf0  mov     rbp, rsp
0x18001adf3  sub     rsp, 50h
0x18001adf7  mov     rax, cs:__security_cookie
0x18001adfe  xor     rax, rsp
0x18001ae01  mov     [rbp+var_10], rax
0x18001ae05  mov     esi, edx
0x18001ae07  mov     rdi, rcx
0x18001ae0a  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001ae0e  mov     r14, r9
0x18001ae11  lea     rcx, [rbp+var_20]; this
0x18001ae15  mov     r13, r8
0x18001ae18  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001ae1d  cmp     qword ptr [rdi+28h], 0
0x18001ae22  jnz     short loc_18001AE2B
0x18001ae24  mov     ebx, 0C00D07F6h
0x18001ae29  jmp     short loc_18001AE6E
0x18001ae2b  test    r14, r14
0x18001ae2e  jz      loc_18001B03B
0x18001ae34  mov     eax, 18h
0x18001ae39  test    esi, esi
0x18001ae3b  jz      short loc_18001AE66
0x18001ae3d  test    r13, r13
0x18001ae40  jz      loc_18001B03B
0x18001ae46  cmp     esi, eax
0x18001ae48  jb      short loc_18001AE66
0x18001ae4a  movups  xmm0, xmmword ptr [r13+0]
0x18001ae4f  mov     [rbp+var_18], eax
0x18001ae52  movdqu  xmmword ptr [rdi+30h], xmm0
0x18001ae57  mov     rcx, [r13+10h]
0x18001ae5b  mov     [rdi+40h], rcx
0x18001ae5f  cmp     rsi, rcx
0x18001ae62  jnb     short loc_18001AE7E
0x18001ae64  mov     eax, ecx
0x18001ae66  mov     ebx, 0C00D07D1h
0x18001ae6b  mov     [r14], eax
0x18001ae6e  lea     rcx, [rbp+var_20]; this
0x18001ae72  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001ae77  mov     eax, ebx
0x18001ae79  jmp     loc_18001B049
0x18001ae7e  mov     r8d, esi; unsigned int
0x18001ae81  lea     rcx, [rbp+var_18]; unsigned int *
0x18001ae85  mov     edx, 8; unsigned int
0x18001ae8a  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001ae8f  mov     ebx, 0C00D07D1h
0x18001ae94  cmp     eax, ebx
0x18001ae96  jz      loc_18001B033
0x18001ae9c  mov     eax, [r13+18h]
0x18001aea0  lea     r15, [r13+20h]
0x18001aea4  mov     [rdi+54h], eax
0x18001aea7  mov     edx, [r13+1Ch]; unsigned int
0x18001aeab  mov     [rdi+60h], edx
0x18001aeae  test    edx, edx
0x18001aeb0  jz      short loc_18001AEEF
0x18001aeb2  lea     rcx, [rbp+var_18]; unsigned int *
0x18001aeb6  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001aebb  cmp     eax, ebx
0x18001aebd  jz      loc_18001B033
0x18001aec3  mov     ecx, edx; unsigned __int64
0x18001aec5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001aeca  mov     [rdi+58h], rax
0x18001aece  test    rax, rax
0x18001aed1  jz      loc_18001AFA0
0x18001aed7  mov     r8d, [rdi+60h]; Size
0x18001aedb  mov     rdx, r15; Src
0x18001aede  mov     rcx, rax; void *
0x18001aee1  call    memcpy_0
0x18001aee6  mov     r10d, [rdi+60h]
0x18001aeea  add     r10, r15
0x18001aeed  jmp     short loc_18001AEF2
0x18001aeef  mov     r10, r15
0x18001aef2  mov     r8d, esi; unsigned int
0x18001aef5  lea     rcx, [rbp+var_18]; unsigned int *
0x18001aef9  mov     edx, 4; unsigned int
0x18001aefe  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001af03  cmp     eax, ebx
0x18001af05  jz      loc_18001B033
0x18001af0b  mov     r15d, [r10]
0x18001af0e  lea     r12, [r10+4]
0x18001af12  test    r15d, r15d
0x18001af15  jz      short loc_18001AF59
0x18001af17  mov     edx, r15d; unsigned int
0x18001af1a  lea     rcx, [rbp+var_18]; unsigned int *
0x18001af1e  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001af23  cmp     eax, ebx
0x18001af25  jz      loc_18001B033
0x18001af2b  mov     ecx, r15d; unsigned __int64
0x18001af2e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001af33  mov     [rdi+68h], rax
0x18001af37  test    rax, rax
0x18001af3a  jz      short loc_18001AFA0
0x18001af3c  mov     r8d, r15d; Size
0x18001af3f  mov     rdx, r12; Src
0x18001af42  mov     rcx, rax; void *
0x18001af45  call    memcpy_0
0x18001af4a  mov     rax, [rdi+68h]
0x18001af4e  lea     ecx, [r15-1]
0x18001af52  add     r12, r15
0x18001af55  mov     byte ptr [rcx+rax], 0
0x18001af59  mov     r8d, esi; unsigned int
0x18001af5c  lea     rcx, [rbp+var_18]; unsigned int *
0x18001af60  mov     edx, 4; unsigned int
0x18001af65  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001af6a  cmp     eax, ebx
0x18001af6c  jz      loc_18001B033
0x18001af72  mov     r15d, [r12]
0x18001af76  test    r15d, r15d
0x18001af79  jz      short loc_18001AFC6
0x18001af7b  mov     edx, r15d; unsigned int
0x18001af7e  lea     rcx, [rbp+var_18]; unsigned int *
0x18001af82  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001af87  cmp     eax, ebx
0x18001af89  jz      loc_18001B033
0x18001af8f  mov     ecx, r15d; unsigned __int64
0x18001af92  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001af97  mov     [rdi+70h], rax
0x18001af9b  test    rax, rax
0x18001af9e  jnz     short loc_18001AFAA
0x18001afa0  mov     ebx, 8007000Eh
0x18001afa5  jmp     loc_18001AE6E
0x18001afaa  lea     rdx, [r12+4]; Src
0x18001afaf  mov     r8, r15; Size
0x18001afb2  mov     rcx, rax; void *
0x18001afb5  call    memcpy_0
0x18001afba  mov     rax, [rdi+70h]
0x18001afbe  lea     ecx, [r15-1]
0x18001afc2  mov     byte ptr [rcx+rax], 0
0x18001afc6  mov     eax, [rbp+var_18]
0x18001afc9  mov     [r14], eax
0x18001afcc  mov     rcx, [rdi+28h]
0x18001afd0  test    rcx, rcx
0x18001afd3  jz      short loc_18001B026
0x18001afd5  mov     qword ptr [rbp+var_18], 0
0x18001afdd  lea     r8, [rbp+var_18]
0x18001afe1  mov     rax, [rcx]
0x18001afe4  lea     rdx, IID_IASFReadWriteTracker
0x18001afeb  mov     rax, [rax]
0x18001afee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff3  test    eax, eax
0x18001aff5  js      short loc_18001B026
0x18001aff7  mov     rcx, qword ptr [rbp+var_18]
0x18001affb  lea     r9, [rdi+30h]
0x18001afff  mov     r8d, [r14]
0x18001b002  mov     rdx, r13
0x18001b005  mov     rax, [rcx]
0x18001b008  mov     rax, [rax+48h]
0x18001b00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b011  mov     rcx, qword ptr [rbp+var_18]
0x18001b015  test    rcx, rcx
0x18001b018  jz      short loc_18001B026
0x18001b01a  mov     rax, [rcx]
0x18001b01d  mov     rax, [rax+10h]
0x18001b021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b026  lea     rcx, [rbp+var_20]; this
0x18001b02a  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001b02f  xor     eax, eax
0x18001b031  jmp     short loc_18001B049
0x18001b033  mov     eax, [rbp+var_18]
0x18001b036  jmp     loc_18001AE6B
0x18001b03b  lea     rcx, [rbp+var_20]; this
0x18001b03f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001b044  mov     eax, 80070057h
0x18001b049  mov     rcx, [rbp+var_10]
0x18001b04d  xor     rcx, rsp; StackCookie
0x18001b050  call    __security_check_cookie
0x18001b055  mov     rbx, [rsp+50h+arg_8]
0x18001b05d  add     rsp, 50h
0x18001b061  pop     r15
0x18001b063  pop     r14
0x18001b065  pop     r13
0x18001b067  pop     r12
0x18001b069  pop     rdi
0x18001b06a  pop     rsi
0x18001b06b  pop     rbp
0x18001b06c  retn
```
