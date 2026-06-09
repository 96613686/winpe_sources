# CASFScriptCommandObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18000c5d0`
- end: `0x18000c9a2`
- name: `?Read@CASFScriptCommandObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `978`
- prototype: `int(CASFScriptCommandObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000c334`
- `0x18000c36c`
- `0x18000c5d0`
- `0x18002e900`
- `0x18002ed90`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  unsigned __int64 v10; // rcx
  unsigned __int8 *v11; // r13
  unsigned __int16 v12; // cx
  int v13; // eax
  unsigned int v14; // edx
  unsigned __int64 v15; // r10
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // kr00_8
  char *v19; // r12
  unsigned __int16 v20; // r10
  const void *v21; // rdx
  size_t v22; // r13
  struct IWMSCriticalSection *v23; // rcx
  int i; // eax
  unsigned int v25; // edx
  unsigned int v26; // r8d
  unsigned int v27; // edx
  __int64 v28; // rax
  unsigned __int16 v29; // r10
  const void *v30; // rdx
  size_t v31; // r13
  __int128 v32; // xmm0
  struct IWMSCriticalSection *v33; // rcx
  GUID *v34; // r12
  unsigned int v36; // [rsp+30h] [rbp-39h] BYREF
  int v37; // [rsp+34h] [rbp-35h]
  unsigned __int16 v38; // [rsp+38h] [rbp-31h]
  unsigned __int16 v39; // [rsp+3Ah] [rbp-2Fh]
  char v40[8]; // [rsp+40h] [rbp-29h] BYREF
  GUID *v41; // [rsp+48h] [rbp-21h]
  __int128 v42; // [rsp+50h] [rbp-19h] BYREF
  char *v43; // [rsp+60h] [rbp-9h]
  unsigned __int8 *v44; // [rsp+70h] [rbp+7h] BYREF
  __int64 v45; // [rsp+78h] [rbp+Fh] BYREF
  int v46; // [rsp+80h] [rbp+17h]

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v40, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_41:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v40);
    return v8;
  }
  if ( a4 )
  {
    if ( !(_DWORD)v4 )
      goto LABEL_39;
    if ( a3 )
    {
      if ( (unsigned int)v4 >= 0x2C )
      {
        (*((void (__fastcall **)(struct IWMSCriticalSection **))*this + 14))(this);
        v9 = *(_OWORD *)a3;
        v41 = (GUID *)(this + 6);
        *((_OWORD *)this + 3) = v9;
        v10 = *((_QWORD *)a3 + 2);
        this[8] = (struct IWMSCriticalSection *)v10;
        if ( v4 >= v10 )
        {
          v11 = a3 + 44;
          v12 = *((_WORD *)a3 + 21);
          v13 = 0;
          v39 = *((_WORD *)a3 + 20);
          v36 = 44;
          v8 = -1072887855;
          v38 = v12;
          while ( 1 )
          {
            v37 = v13;
            if ( (unsigned __int16)v13 >= v12 )
            {
              v23 = this[5];
              v45 = 0;
              v46 = 0;
              ASFGetTimeBase(v23, 0, &v45);
              for ( i = 0; ; LOWORD(i) = v37 + 1 )
              {
                v37 = i;
                if ( (unsigned __int16)i >= v39 )
                  break;
                v43 = 0;
                v42 = 0;
                if ( (unsigned int)CHECK_FOR_SPACE(&v36, 4u, v4) == -1072887855 )
                  goto LABEL_23;
                ASFTimeToPresTime(&v45, 10000LL * *(unsigned int *)v11, &v42);
                if ( (unsigned int)CHECK_FOR_SPACE(&v36, 2u, v4) == -1072887855 )
                  goto LABEL_23;
                WORD6(v42) = *((_WORD *)v11 + 2);
                if ( (unsigned int)CHECK_FOR_SPACE(&v36, v25, v26) == -1072887855 )
                  goto LABEL_23;
                v28 = *((unsigned __int16 *)v11 + 3);
                LODWORD(v44) = *((unsigned __int16 *)v11 + 3);
                v19 = (char *)operator new[](saturated_mul(v28 + 1, v27));
                if ( !v19 )
                  goto LABEL_21;
                if ( (unsigned int)CHECK_FOR_SPACE(&v36, 2 * (int)v44, v4) == -1072887855 )
                  goto LABEL_22;
                v44 = v11 + 8;
                v30 = v11 + 8;
                v31 = 2LL * v29;
                memcpy_0(v19, v30, v31);
                v32 = v42;
                v43 = v19;
                *(_WORD *)&v19[v31] = 0;
                v42 = v32;
                if ( !(unsigned int)CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(this + 38, &v42) )
                  goto LABEL_20;
                v11 = &v44[v31];
                HIWORD(i) = HIWORD(v37);
              }
              *a4 = v36;
              v33 = this[5];
              if ( v33
                && (v44 = 0,
                    (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, unsigned __int8 **))v33)(
                      v33,
                      &IID_IASFReadWriteTracker,
                      &v44) >= 0) )
              {
                v34 = (GUID *)(this + 6);
                (*(void (__fastcall **)(unsigned __int8 *, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v44 + 72LL))(
                  v44,
                  a3,
                  *a4,
                  (char *)this + 48);
                if ( v44 )
                  (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v44 + 16LL))(v44);
              }
              else
              {
                v34 = v41;
              }
              *v34 = CLSID_ASFScriptCommandObject;
              CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v40);
              return 0;
            }
            if ( (unsigned int)CHECK_FOR_SPACE(&v36, 2u, v4) == -1072887855 )
              goto LABEL_23;
            v16 = *(unsigned __int16 *)v11;
            LODWORD(v44) = *(unsigned __int16 *)v11;
            v18 = v16 + 1;
            v17 = (v16 + 1) * v14;
            if ( !is_mul_ok(v18, v14) )
              v17 = v15;
            v19 = (char *)operator new[](v17);
            if ( !v19 )
              goto LABEL_21;
            if ( (unsigned int)CHECK_FOR_SPACE(&v36, 2 * (int)v44, v4) == -1072887855 )
              break;
            v44 = v11 + 2;
            v21 = v11 + 2;
            v22 = 2LL * v20;
            memcpy_0(v19, v21, v22);
            *(_WORD *)&v19[v22] = 0;
            if ( !(unsigned int)CTDynArray<unsigned short *,20>::Add(this + 10, v19, 0) )
            {
LABEL_20:
              operator delete(v19);
LABEL_21:
              v8 = -2147024882;
              goto LABEL_41;
            }
            v11 = &v44[v22];
            HIWORD(v13) = HIWORD(v37);
            v12 = v38;
            LOWORD(v13) = v37 + 1;
          }
LABEL_22:
          operator delete(v19);
LABEL_23:
          *a4 = v36;
          goto LABEL_41;
        }
        if ( v10 >= 0x100000000LL )
        {
          v8 = -1072887821;
          goto LABEL_41;
        }
        *a4 = *((_DWORD *)this + 16);
LABEL_40:
        v8 = -1072887855;
        goto LABEL_41;
      }
LABEL_39:
      *a4 = 44;
      goto LABEL_40;
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v40);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000c5d0  mov     [rsp-8+arg_8], rbx
0x18000c5d5  push    rbp
0x18000c5d6  push    rsi
0x18000c5d7  push    rdi
0x18000c5d8  push    r12
0x18000c5da  push    r13
0x18000c5dc  push    r14
0x18000c5de  push    r15
0x18000c5e0  lea     rbp, [rsp-27h]
0x18000c5e5  sub     rsp, 90h
0x18000c5ec  mov     rax, cs:__security_cookie
0x18000c5f3  xor     rax, rsp
0x18000c5f6  mov     [rbp+57h+var_38], rax
0x18000c5fa  mov     r14d, edx
0x18000c5fd  mov     rsi, rcx
0x18000c600  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000c604  mov     rdi, r9
0x18000c607  lea     rcx, [rbp+57h+var_80]; this
0x18000c60b  mov     r15, r8
0x18000c60e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000c613  cmp     qword ptr [rsi+28h], 0
0x18000c618  jnz     short loc_18000C624
0x18000c61a  mov     ebx, 0C00D07F6h
0x18000c61f  jmp     loc_18000C960
0x18000c624  test    rdi, rdi
0x18000c627  jz      loc_18000C96D
0x18000c62d  mov     ebx, 2Ch ; ','
0x18000c632  test    r14d, r14d
0x18000c635  jz      loc_18000C959
0x18000c63b  test    r15, r15
0x18000c63e  jz      loc_18000C96D
0x18000c644  cmp     r14d, ebx
0x18000c647  jb      loc_18000C959
0x18000c64d  mov     rax, [rsi]
0x18000c650  mov     rcx, rsi
0x18000c653  mov     rax, [rax+70h]
0x18000c657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65c  movups  xmm0, xmmword ptr [r15]
0x18000c660  lea     r12, [rsi+30h]
0x18000c664  mov     [rbp+57h+var_78], r12
0x18000c668  movdqu  xmmword ptr [r12], xmm0
0x18000c66e  mov     rcx, [r15+10h]
0x18000c672  mov     [rsi+40h], rcx
0x18000c676  cmp     r14, rcx
0x18000c679  jnb     short loc_18000C69E
0x18000c67b  mov     rax, 100000000h
0x18000c685  cmp     rcx, rax
0x18000c688  jb      short loc_18000C694
0x18000c68a  mov     ebx, 0C00D07F3h
0x18000c68f  jmp     loc_18000C960
0x18000c694  mov     eax, [rsi+40h]
0x18000c697  mov     [rdi], eax
0x18000c699  jmp     loc_18000C95B
0x18000c69e  movzx   r12d, word ptr [r15+28h]
0x18000c6a3  lea     r13, [r15+2Ch]
0x18000c6a7  movzx   ecx, word ptr [r15+2Ah]
0x18000c6ac  xor     eax, eax
0x18000c6ae  mov     [rbp+57h+var_86], r12w
0x18000c6b3  mov     [rbp+57h+var_90], ebx
0x18000c6b6  mov     ebx, 0C00D07D1h
0x18000c6bb  mov     [rbp+57h+var_88], cx
0x18000c6bf  lea     r12d, [rax+1]
0x18000c6c3  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000c6c7  mov     [rbp+57h+var_8C], eax
0x18000c6ca  cmp     ax, cx
0x18000c6cd  jnb     loc_18000C79E
0x18000c6d3  mov     r8d, r14d; unsigned int
0x18000c6d6  lea     edx, [r10+3]; unsigned int
0x18000c6da  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c6de  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c6e3  cmp     eax, ebx
0x18000c6e5  jz      loc_18000C794
0x18000c6eb  movzx   eax, word ptr [r13+0]
0x18000c6f0  mov     dword ptr [rbp+57h+var_50], eax
0x18000c6f3  lea     rcx, [r12+rax]
0x18000c6f7  mov     eax, edx
0x18000c6f9  mul     rcx
0x18000c6fc  cmovb   rax, r10
0x18000c700  mov     rcx, rax; unsigned __int64
0x18000c703  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c708  mov     r12, rax
0x18000c70b  test    rax, rax
0x18000c70e  jz      short loc_18000C782
0x18000c710  mov     r10d, dword ptr [rbp+57h+var_50]
0x18000c714  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c718  mov     r8d, r14d; unsigned int
0x18000c71b  lea     edx, [r10+r10]; unsigned int
0x18000c71f  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c724  cmp     eax, ebx
0x18000c726  jz      short loc_18000C78C
0x18000c728  lea     rcx, [r13+2]
0x18000c72c  movzx   eax, r10w
0x18000c730  mov     [rbp+57h+var_50], rcx
0x18000c734  mov     rdx, rcx; Src
0x18000c737  mov     rcx, r12; void *
0x18000c73a  lea     r13, [rax+rax]
0x18000c73e  mov     r8, r13; Size
0x18000c741  call    memcpy_0
0x18000c746  xor     eax, eax
0x18000c748  lea     rcx, [rsi+50h]
0x18000c74c  xor     r8d, r8d
0x18000c74f  mov     [r12+r13], ax
0x18000c754  mov     rdx, r12
0x18000c757  call    ?Add@?$CTDynArray@PEAG$0BE@@@QEAAHPEAGPEAK@Z; CTDynArray<ushort *,20>::Add(ushort *,ulong *)
0x18000c75c  test    eax, eax
0x18000c75e  jz      short loc_18000C77A
0x18000c760  add     r13, [rbp+57h+var_50]
0x18000c764  mov     r12d, 1
0x18000c76a  mov     eax, [rbp+57h+var_8C]
0x18000c76d  movzx   ecx, [rbp+57h+var_88]
0x18000c771  add     ax, r12w
0x18000c775  jmp     loc_18000C6C3
0x18000c77a  mov     rcx, r12; Block
0x18000c77d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c782  mov     ebx, 8007000Eh
0x18000c787  jmp     loc_18000C960
0x18000c78c  mov     rcx, r12; Block
0x18000c78f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c794  mov     eax, [rbp+57h+var_90]
0x18000c797  mov     [rdi], eax
0x18000c799  jmp     loc_18000C960
0x18000c79e  mov     rcx, [rsi+28h]
0x18000c7a2  lea     r8, [rbp+57h+var_48]
0x18000c7a6  xor     eax, eax
0x18000c7a8  xor     edx, edx
0x18000c7aa  mov     [rbp+57h+var_48], rax
0x18000c7ae  mov     [rbp+57h+var_40], eax
0x18000c7b1  call    ASFGetTimeBase
0x18000c7b6  xor     eax, eax
0x18000c7b8  mov     [rbp+57h+var_8C], eax
0x18000c7bb  cmp     ax, [rbp+57h+var_86]
0x18000c7bf  jnb     loc_18000C8D7
0x18000c7c5  xor     eax, eax
0x18000c7c7  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c7cb  xorps   xmm0, xmm0
0x18000c7ce  mov     [rbp+57h+var_60], rax
0x18000c7d2  mov     r8d, r14d; unsigned int
0x18000c7d5  movups  [rbp+57h+var_70], xmm0
0x18000c7d9  lea     edx, [rax+4]; unsigned int
0x18000c7dc  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c7e1  cmp     eax, ebx
0x18000c7e3  jz      short loc_18000C794
0x18000c7e5  mov     eax, [r13+0]
0x18000c7e9  lea     r8, [rbp+57h+var_70]
0x18000c7ed  imul    rdx, rax, 2710h
0x18000c7f4  lea     rcx, [rbp+57h+var_48]
0x18000c7f8  call    ASFTimeToPresTime
0x18000c7fd  mov     r8d, r14d; unsigned int
0x18000c800  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c804  mov     edx, 2; unsigned int
0x18000c809  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c80e  cmp     eax, ebx
0x18000c810  jz      short loc_18000C794
0x18000c812  movzx   eax, word ptr [r13+4]
0x18000c817  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c81b  mov     word ptr [rbp+57h+var_70+0Ch], ax
0x18000c81f  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c824  cmp     eax, ebx
0x18000c826  jz      loc_18000C794
0x18000c82c  movzx   eax, word ptr [r13+6]
0x18000c831  mov     dword ptr [rbp+57h+var_50], eax
0x18000c834  lea     rcx, [r12+rax]
0x18000c838  mov     eax, edx
0x18000c83a  mul     rcx
0x18000c83d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c844  cmovb   rax, rcx
0x18000c848  mov     rcx, rax; unsigned __int64
0x18000c84b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c850  mov     r12, rax
0x18000c853  test    rax, rax
0x18000c856  jz      loc_18000C782
0x18000c85c  mov     r10d, dword ptr [rbp+57h+var_50]
0x18000c860  lea     rcx, [rbp+57h+var_90]; unsigned int *
0x18000c864  mov     r8d, r14d; unsigned int
0x18000c867  lea     edx, [r10+r10]; unsigned int
0x18000c86b  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18000c870  cmp     eax, ebx
0x18000c872  jz      loc_18000C78C
0x18000c878  lea     rcx, [r13+8]
0x18000c87c  movzx   eax, r10w
0x18000c880  mov     [rbp+57h+var_50], rcx
0x18000c884  mov     rdx, rcx; Src
0x18000c887  mov     rcx, r12; void *
0x18000c88a  lea     r13, [rax+rax]
0x18000c88e  mov     r8, r13; Size
0x18000c891  call    memcpy_0
0x18000c896  movups  xmm0, [rbp+57h+var_70]
0x18000c89a  xor     eax, eax
0x18000c89c  mov     [rbp+57h+var_60], r12
0x18000c8a0  lea     rcx, [rsi+130h]
0x18000c8a7  mov     [r12+r13], ax
0x18000c8ac  lea     rdx, [rbp+57h+var_70]
0x18000c8b0  movaps  [rbp+57h+var_70], xmm0
0x18000c8b4  call    ?Add@?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEAAHUCOMMAND_RECORD@CASFScriptCommandObjectBase@@PEAK@Z; CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(CASFScriptCommandObjectBase::COMMAND_RECORD,ulong *)
0x18000c8b9  test    eax, eax
0x18000c8bb  jz      loc_18000C77A
0x18000c8c1  add     r13, [rbp+57h+var_50]
0x18000c8c5  mov     r12d, 1
0x18000c8cb  mov     eax, [rbp+57h+var_8C]
0x18000c8ce  add     ax, r12w
0x18000c8d2  jmp     loc_18000C7B8
0x18000c8d7  mov     eax, [rbp+57h+var_90]
0x18000c8da  mov     [rdi], eax
0x18000c8dc  mov     rcx, [rsi+28h]
0x18000c8e0  test    rcx, rcx
0x18000c8e3  jz      short loc_18000C93B
0x18000c8e5  mov     [rbp+57h+var_50], 0
0x18000c8ed  lea     r8, [rbp+57h+var_50]
0x18000c8f1  mov     rax, [rcx]
0x18000c8f4  lea     rdx, IID_IASFReadWriteTracker
0x18000c8fb  mov     rax, [rax]
0x18000c8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c903  test    eax, eax
0x18000c905  js      short loc_18000C93B
0x18000c907  mov     rcx, [rbp+57h+var_50]
0x18000c90b  lea     r12, [rsi+30h]
0x18000c90f  mov     r8d, [rdi]
0x18000c912  mov     r9, r12
0x18000c915  mov     rdx, r15
0x18000c918  mov     rax, [rcx]
0x18000c91b  mov     rax, [rax+48h]
0x18000c91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c924  mov     rcx, [rbp+57h+var_50]
0x18000c928  test    rcx, rcx
0x18000c92b  jz      short loc_18000C93F
0x18000c92d  mov     rax, [rcx]
0x18000c930  mov     rax, [rax+10h]
0x18000c934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c939  jmp     short loc_18000C93F
0x18000c93b  mov     r12, [rbp+57h+var_78]
0x18000c93f  movups  xmm0, xmmword ptr cs:CLSID_ASFScriptCommandObject.Data1
0x18000c946  lea     rcx, [rbp+57h+var_80]; this
0x18000c94a  movdqu  xmmword ptr [r12], xmm0
0x18000c950  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000c955  xor     eax, eax
0x18000c957  jmp     short loc_18000C97B
0x18000c959  mov     [rdi], ebx
0x18000c95b  mov     ebx, 0C00D07D1h
0x18000c960  lea     rcx, [rbp+57h+var_80]; this
0x18000c964  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000c969  mov     eax, ebx
0x18000c96b  jmp     short loc_18000C97B
0x18000c96d  lea     rcx, [rbp+57h+var_80]; this
0x18000c971  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000c976  mov     eax, 80070057h
0x18000c97b  mov     rcx, [rbp+57h+var_38]
0x18000c97f  xor     rcx, rsp; StackCookie
0x18000c982  call    __security_check_cookie
0x18000c987  mov     rbx, [rsp+0C0h+arg_8]
0x18000c98f  add     rsp, 90h
0x18000c996  pop     r15
0x18000c998  pop     r14
0x18000c99a  pop     r13
0x18000c99c  pop     r12
0x18000c99e  pop     rdi
0x18000c99f  pop     rsi
0x18000c9a0  pop     rbp
0x18000c9a1  retn
```
