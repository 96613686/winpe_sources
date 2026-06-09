# CASFScriptCommandObjectBase::GetScriptCommand(ushort,_ASF_PRES_TIMESTAMP *,ulong,ushort *,ulong *,ulong,ushort *,ulong *)

- ea: `0x180021d30`
- end: `0x180021f2e`
- name: `?GetScriptCommand@CASFScriptCommandObjectBase@@UEAAJGPEAU_ASF_PRES_TIMESTAMP@@KPEAGPEAKK12@Z`
- size: `510`
- prototype: `int(CASFScriptCommandObjectBase *__hidden this, unsigned __int16, struct _ASF_PRES_TIMESTAMP *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18000f12c`
- `0x18000ff88`
- `0x180021d30`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::GetScriptCommand(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        struct _ASF_PRES_TIMESTAMP *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned int *a9)
{
  unsigned int v9; // ebx
  unsigned __int64 v12; // r15
  unsigned int v13; // ebx
  unsigned int *v14; // r14
  unsigned int *v15; // r12
  char *v16; // rdx
  unsigned int v17; // ecx
  char *v18; // rbx
  int v19; // r9d
  unsigned int v20; // r8d
  unsigned int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // edx
  unsigned __int16 *v27; // rax
  char v29; // [rsp+60h] [rbp+8h] BYREF

  v9 = a2;
  v12 = a4;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v29, this[4]);
  if ( !this[5] )
  {
    v13 = -1072887818;
LABEL_32:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v29);
    return v13;
  }
  if ( a3 )
  {
    v14 = a6;
    if ( a6 )
    {
      if ( a5 || !(_DWORD)v12 )
      {
        v15 = a9;
        if ( a9 )
        {
          if ( a8 || !a7 )
          {
            v16 = (char *)(this + 38);
            v17 = v9;
            if ( v9 < *((_DWORD *)this + 214) )
            {
              v18 = 0;
              v19 = -2147467259;
              while ( 1 )
              {
                if ( !v16 )
                  goto LABEL_19;
                v20 = *((_DWORD *)v16 + 2);
                if ( v17 >= v20 && v17 < v20 + 20 )
                  break;
                v16 = (char *)*((_QWORD *)v16 + 66);
              }
              v21 = v17 - v20;
              if ( ((unsigned __int8)v16[((unsigned __int64)v21 >> 3) + 40]
                  & (unsigned __int8)CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks[v21 & 7]) == 0 )
                goto LABEL_31;
              v19 = 0;
              v18 = &v16[24 * v21 + 48];
LABEL_19:
              if ( v19 < 0 )
                v18 = 0;
              if ( !v18 || (unsigned int)*((unsigned __int16 *)v18 + 6) >= *((_DWORD *)this + 74) )
              {
LABEL_31:
                v13 = -1072887838;
                goto LABEL_32;
              }
              *(_QWORD *)a3 = *(_QWORD *)v18;
              *((_DWORD *)a3 + 2) = *((_DWORD *)v18 + 2);
              v22 = CTDynArray<unsigned short *,20>::operator[](this + 10, *((unsigned __int16 *)v18 + 6));
              v23 = -1;
              v24 = v22;
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)(v24 + 2 * v25) );
              *v14 = v25 + 1;
              do
                ++v23;
              while ( *(_WORD *)(*((_QWORD *)v18 + 2) + 2 * v23) );
              v26 = v23 + 1;
              *v15 = v26;
              if ( *v14 <= (unsigned int)v12 && v26 <= a7 )
              {
                v27 = (unsigned __int16 *)CTDynArray<unsigned short *,20>::operator[](
                                            this + 10,
                                            *((unsigned __int16 *)v18 + 6));
                StringCchCopyW(a5, v12, v27);
                StringCchCopyW(a8, a7, *((unsigned __int16 **)v18 + 2));
                CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v29);
                return 0;
              }
              v13 = -1072887855;
            }
            else
            {
              v13 = -1072887824;
            }
            goto LABEL_32;
          }
        }
      }
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v29);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180021d30  push    rbx
0x180021d32  push    rbp
0x180021d33  push    rdi
0x180021d34  push    r12
0x180021d36  push    r14
0x180021d38  push    r15
0x180021d3a  sub     rsp, 28h
0x180021d3e  movzx   ebx, dx
0x180021d41  mov     rdi, rcx
0x180021d44  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180021d48  mov     rbp, r8
0x180021d4b  lea     rcx, [rsp+58h+arg_0]; this
0x180021d50  mov     r15d, r9d
0x180021d53  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180021d58  xor     r10d, r10d
0x180021d5b  cmp     [rdi+28h], r10
0x180021d5f  jnz     short loc_180021D6B
0x180021d61  mov     ebx, 0C00D07F6h
0x180021d66  jmp     loc_180021F03
0x180021d6b  test    rbp, rbp
0x180021d6e  jz      loc_180021F11
0x180021d74  mov     r14, [rsp+58h+arg_28]
0x180021d7c  test    r14, r14
0x180021d7f  jz      loc_180021F11
0x180021d85  cmp     [rsp+58h+arg_20], r10
0x180021d8d  jnz     short loc_180021D98
0x180021d8f  test    r15d, r15d
0x180021d92  jnz     loc_180021F11
0x180021d98  mov     r12, [rsp+58h+arg_40]
0x180021da0  test    r12, r12
0x180021da3  jz      loc_180021F11
0x180021da9  cmp     [rsp+58h+arg_38], r10
0x180021db1  jnz     short loc_180021DC1
0x180021db3  cmp     [rsp+58h+arg_30], r10d
0x180021dbb  jnz     loc_180021F11
0x180021dc1  lea     rdx, [rdi+130h]
0x180021dc8  mov     ecx, ebx
0x180021dca  cmp     ebx, [rdx+228h]
0x180021dd0  jb      short loc_180021DDC
0x180021dd2  mov     ebx, 0C00D07F0h
0x180021dd7  jmp     loc_180021F03
0x180021ddc  mov     rbx, r10
0x180021ddf  mov     r9d, 80004005h
0x180021de5  test    rdx, rdx
0x180021de8  jz      short loc_180021E37
0x180021dea  mov     r8d, [rdx+8]
0x180021dee  cmp     ecx, r8d
0x180021df1  jb      short loc_180021DFB
0x180021df3  lea     eax, [r8+14h]
0x180021df7  cmp     ecx, eax
0x180021df9  jb      short loc_180021E04
0x180021dfb  mov     rdx, [rdx+210h]
0x180021e02  jmp     short loc_180021DE5
0x180021e04  sub     ecx, r8d
0x180021e07  lea     r9, ?s_bSingleBitMasks@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::s_bSingleBitMasks
0x180021e0e  mov     eax, ecx
0x180021e10  shr     rax, 3
0x180021e14  mov     r8d, ecx
0x180021e17  and     ecx, 7
0x180021e1a  mov     al, [rax+rdx+28h]
0x180021e1e  test    [rcx+r9], al
0x180021e22  jz      loc_180021EFE
0x180021e28  lea     rax, [r8+2]
0x180021e2c  mov     r9d, r10d
0x180021e2f  lea     rax, [rax+rax*2]
0x180021e33  lea     rbx, [rdx+rax*8]
0x180021e37  test    r9d, r9d
0x180021e3a  cmovs   rbx, r10
0x180021e3e  test    rbx, rbx
0x180021e41  jz      loc_180021EFE
0x180021e47  movzx   eax, word ptr [rbx+0Ch]
0x180021e4b  cmp     eax, [rdi+128h]
0x180021e51  jnb     loc_180021EFE
0x180021e57  movsd   xmm0, qword ptr [rbx]
0x180021e5b  lea     rcx, [rdi+50h]
0x180021e5f  movsd   qword ptr [rbp+0], xmm0
0x180021e64  mov     eax, [rbx+8]
0x180021e67  mov     [rbp+8], eax
0x180021e6a  movzx   edx, word ptr [rbx+0Ch]
0x180021e6e  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x180021e73  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180021e77  mov     rcx, rax
0x180021e7a  mov     rax, rdx
0x180021e7d  xor     r8d, r8d
0x180021e80  inc     rax
0x180021e83  cmp     [rcx+rax*2], r8w
0x180021e88  jnz     short loc_180021E80
0x180021e8a  inc     eax
0x180021e8c  mov     [r14], eax
0x180021e8f  mov     rax, [rbx+10h]
0x180021e93  inc     rdx
0x180021e96  cmp     [rax+rdx*2], r8w
0x180021e9b  jnz     short loc_180021E93
0x180021e9d  inc     edx
0x180021e9f  mov     [r12], edx
0x180021ea3  cmp     [r14], r15d
0x180021ea6  ja      short loc_180021EF7
0x180021ea8  cmp     edx, [rsp+58h+arg_30]
0x180021eaf  ja      short loc_180021EF7
0x180021eb1  movzx   edx, word ptr [rbx+0Ch]
0x180021eb5  lea     rcx, [rdi+50h]
0x180021eb9  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x180021ebe  mov     rcx, [rsp+58h+arg_20]; unsigned __int16 *
0x180021ec6  mov     r8, rax; unsigned __int16 *
0x180021ec9  mov     rdx, r15; unsigned __int64
0x180021ecc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021ed1  mov     edx, [rsp+58h+arg_30]; unsigned __int64
0x180021ed8  mov     r8, [rbx+10h]; unsigned __int16 *
0x180021edc  mov     rcx, [rsp+58h+arg_38]; unsigned __int16 *
0x180021ee4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021ee9  lea     rcx, [rsp+58h+arg_0]; this
0x180021eee  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021ef3  xor     eax, eax
0x180021ef5  jmp     short loc_180021F20
0x180021ef7  mov     ebx, 0C00D07D1h
0x180021efc  jmp     short loc_180021F03
0x180021efe  mov     ebx, 0C00D07E2h
0x180021f03  lea     rcx, [rsp+58h+arg_0]; this
0x180021f08  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021f0d  mov     eax, ebx
0x180021f0f  jmp     short loc_180021F20
0x180021f11  lea     rcx, [rsp+58h+arg_0]; this
0x180021f16  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180021f1b  mov     eax, 80070057h
0x180021f20  add     rsp, 28h
0x180021f24  pop     r15
0x180021f26  pop     r14
0x180021f28  pop     r12
0x180021f2a  pop     rdi
0x180021f2b  pop     rbp
0x180021f2c  pop     rbx
0x180021f2d  retn
```
