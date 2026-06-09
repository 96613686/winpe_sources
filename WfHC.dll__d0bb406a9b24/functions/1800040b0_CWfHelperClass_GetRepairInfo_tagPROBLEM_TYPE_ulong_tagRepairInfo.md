# CWfHelperClass::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x1800040b0`
- end: `0x18000433d`
- name: `?GetRepairInfo@CWfHelperClass@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003c10`
- `0x1800040b0`
- `0x180005e60`
- `0x180007580`
- `0x18000c566`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800041d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800041d6`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::GetRepairInfo(
        CWfHelperClass *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  struct tagRepairInfo *v5; // r12
  unsigned int v6; // r13d
  int v7; // eax
  int updated; // ebx
  int v9; // ecx
  __int64 v10; // rax
  struct tagRepairInfo *v11; // rax
  struct tagRepairInfo *v12; // r14
  int v13; // esi
  unsigned int v14; // ebx
  unsigned __int64 v15; // rcx
  const struct tagRepairInfoMap *v16; // rdi
  int v18; // [rsp+20h] [rbp-68h]
  _OWORD v19[4]; // [rsp+40h] [rbp-48h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v18 = 0;
  if ( *((_DWORD *)this + 43) )
  {
    v19[0] = ID_FW_LOWH_REPAIR_REPRO_MODE;
  }
  else
  {
    if ( !*((_QWORD *)this + 20) )
    {
      updated = 0;
      *a3 = 0;
      *a4 = 0;
      goto LABEL_32;
    }
    v9 = *(_DWORD *)(*((_QWORD *)this + 20) + 4LL);
    v10 = 0;
    if ( dword_180015920 == v9 )
      goto LABEL_15;
    v10 = 1;
    if ( dword_180015934 == v9 )
      goto LABEL_15;
    v10 = 2;
    if ( dword_180015948 == v9
      || (v10 = 3, dword_18001595C == v9)
      || (v10 = 4, dword_180015970 == v9)
      || (v10 = 5, dword_180015984 == v9)
      || (v10 = 6, dword_180015998 == v9)
      || (v10 = 7, dword_1800159AC == v9)
      || (v10 = 8, dword_1800159C0 == v9)
      || (v10 = 9, dword_1800159D4 == v9) )
    {
LABEL_15:
      v19[0] = *(__int128 *)((char *)&xmmword_180015910 + 20 * v10);
    }
    else
    {
      v19[0] = GUID_NULL;
    }
  }
  v11 = (struct tagRepairInfo *)CoTaskMemAlloc(0x70u);
  v12 = v11;
  if ( v11 )
  {
    v11->guid = 0;
    *(_OWORD *)&v11->pwszClassName = 0;
    *(_OWORD *)&v11->sidType = 0;
    *(_OWORD *)&v11->risk = 0;
    *(_OWORD *)&v11->UiInfo.pwzNull = 0;
    *((_OWORD *)&v11->UiInfo.pwzDui + 1) = 0;
    *((_OWORD *)&v11->UiInfo.pwzDui + 2) = 0;
    v13 = 0;
    while ( 2 )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = 120LL * v14;
        v16 = (const struct tagRepairInfoMap *)((char *)&CWfHelperClass::m_repairInfos + v15);
        if ( a2 == *(_DWORD *)((char *)&CWfHelperClass::m_repairInfos + v15)
          && !memcmp_0(&v19[v13], &qword_180015118[v15 / 8], 0x10u) )
        {
          break;
        }
        if ( ++v14 >= 0xB )
        {
          updated = -2147023728;
          goto LABEL_30;
        }
      }
      updated = PopulateRepairInfo(v16, &v12[v13]);
      if ( updated < 0 )
      {
LABEL_30:
        FreeRepairInfos(v12, 1u, 1);
        goto LABEL_31;
      }
      if ( !++v13 )
        continue;
      break;
    }
    v5 = v12;
    v6 = 1;
    v18 = 1;
    updated = CWfHelperClass::UpdateRepairInfoDescription(this, v12);
    if ( updated >= 0 )
    {
      v5 = 0;
      v6 = 0;
      v7 = 0;
      *a4 = v12;
      *a3 = 1;
      goto LABEL_32;
    }
  }
  else
  {
    updated = -2147024882;
  }
LABEL_31:
  v7 = v18;
LABEL_32:
  if ( v5 )
    FreeRepairInfos(v5, v6, v7);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800040b0  mov     [rsp+arg_8], rbx
0x1800040b5  mov     [rsp+arg_18], r9
0x1800040ba  mov     [rsp+arg_10], r8
0x1800040bf  mov     [rsp+arg_0], rcx
0x1800040c4  push    rbp
0x1800040c5  push    rsi
0x1800040c6  push    rdi
0x1800040c7  push    r12
0x1800040c9  push    r13
0x1800040cb  push    r14
0x1800040cd  push    r15
0x1800040cf  sub     rsp, 50h
0x1800040d3  mov     r15d, edx
0x1800040d6  xor     r12d, r12d
0x1800040d9  mov     [rsp+88h+var_60], r12
0x1800040de  xor     r13d, r13d
0x1800040e1  mov     [rsp+88h+var_58], r13
0x1800040e6  xor     eax, eax
0x1800040e8  mov     [rsp+88h+var_68], eax
0x1800040ec  lea     rdi, cs:180000000h
0x1800040f3  cmp     [rcx+0ACh], eax
0x1800040f9  jnz     loc_1800041C5
0x1800040ff  cmp     [rcx+0A0h], rax
0x180004106  jnz     short loc_180004115
0x180004108  xor     ebx, ebx
0x18000410a  mov     [r8], ebx
0x18000410d  mov     [r9], rbx
0x180004110  jmp     loc_180004310
0x180004115  mov     rax, [rcx+0A0h]
0x18000411c  mov     ecx, [rax+4]
0x18000411f  xor     eax, eax
0x180004121  cmp     cs:dword_180015920, ecx
0x180004127  jz      loc_1800041B1
0x18000412d  mov     eax, 1
0x180004132  cmp     cs:dword_180015934, ecx
0x180004138  jz      short loc_1800041B1
0x18000413a  mov     eax, 2
0x18000413f  cmp     cs:dword_180015948, ecx
0x180004145  jz      short loc_1800041B1
0x180004147  mov     eax, 3
0x18000414c  cmp     cs:dword_18001595C, ecx
0x180004152  jz      short loc_1800041B1
0x180004154  mov     eax, 4
0x180004159  cmp     cs:dword_180015970, ecx
0x18000415f  jz      short loc_1800041B1
0x180004161  mov     eax, 5
0x180004166  cmp     cs:dword_180015984, ecx
0x18000416c  jz      short loc_1800041B1
0x18000416e  mov     eax, 6
0x180004173  cmp     cs:dword_180015998, ecx
0x180004179  jz      short loc_1800041B1
0x18000417b  mov     eax, 7
0x180004180  cmp     cs:dword_1800159AC, ecx
0x180004186  jz      short loc_1800041B1
0x180004188  mov     eax, 8
0x18000418d  cmp     cs:dword_1800159C0, ecx
0x180004193  jz      short loc_1800041B1
0x180004195  mov     eax, 9
0x18000419a  cmp     cs:dword_1800159D4, ecx
0x1800041a0  jz      short loc_1800041B1
0x1800041a2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800041a9  movdqa  [rsp+88h+var_48], xmm0
0x1800041af  jmp     short loc_1800041D1
0x1800041b1  lea     rax, [rax+rax*4]
0x1800041b5  movups  xmm0, rva xmmword_180015910[rdi+rax*4]
0x1800041bd  movdqa  [rsp+88h+var_48], xmm0
0x1800041c3  jmp     short loc_1800041D1
0x1800041c5  movups  xmm0, cs:ID_FW_LOWH_REPAIR_REPRO_MODE
0x1800041cc  movups  [rsp+88h+var_48], xmm0
0x1800041d1  mov     ecx, 70h ; 'p'; cb
0x1800041d6  call    cs:__imp_CoTaskMemAlloc
0x1800041dc  mov     r14, rax
0x1800041df  test    rax, rax
0x1800041e2  jnz     short loc_1800041EE
0x1800041e4  mov     ebx, 8007000Eh
0x1800041e9  jmp     loc_18000430C
0x1800041ee  xorps   xmm0, xmm0
0x1800041f1  movups  xmmword ptr [rax], xmm0
0x1800041f4  movups  xmmword ptr [rax+10h], xmm0
0x1800041f8  movups  xmmword ptr [rax+20h], xmm0
0x1800041fc  movups  xmmword ptr [rax+30h], xmm0
0x180004200  movups  xmmword ptr [rax+40h], xmm0
0x180004204  movups  xmmword ptr [rax+50h], xmm0
0x180004208  movups  xmmword ptr [rax+60h], xmm0
0x18000420c  xor     esi, esi
0x18000420e  xchg    ax, ax
0x180004210  xor     ebx, ebx
0x180004212  nop     dword ptr [rax+00h]
0x180004216  nop     word ptr [rax+rax+00000000h]
0x180004220  mov     eax, ebx
0x180004222  imul    rcx, rax, 78h ; 'x'
0x180004226  lea     rdi, rva ?m_repairInfos@CWfHelperClass@@0QBUtagRepairInfoMap@@B[rdi]; tagRepairInfoMap const near * const CWfHelperClass::m_repairInfos ...
0x18000422d  add     rdi, rcx
0x180004230  cmp     r15d, [rdi]
0x180004233  jnz     short loc_180004265
0x180004235  mov     ebp, esi
0x180004237  lea     rax, cs:180000000h
0x18000423e  lea     rdx, rva qword_180015118[rax]
0x180004245  add     rdx, rcx; Buf2
0x180004248  mov     eax, esi
0x18000424a  shl     rax, 4
0x18000424e  lea     rcx, [rsp+88h+var_48]
0x180004253  add     rcx, rax; Buf1
0x180004256  mov     r8d, 10h; Size
0x18000425c  call    memcmp_0
0x180004261  test    eax, eax
0x180004263  jz      short loc_180004279
0x180004265  inc     ebx
0x180004267  cmp     ebx, 0Bh
0x18000426a  jnb     loc_1800042F7
0x180004270  lea     rdi, cs:180000000h
0x180004277  jmp     short loc_180004220
0x180004279  imul    rdx, rbp, 70h ; 'p'
0x18000427d  add     rdx, r14; struct tagRepairInfo *
0x180004280  mov     rcx, rdi; struct tagRepairInfoMap *
0x180004283  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x180004288  mov     ebx, eax
0x18000428a  test    eax, eax
0x18000428c  js      short loc_1800042FC
0x18000428e  inc     esi
0x180004290  cmp     esi, 1
0x180004293  lea     rdi, cs:180000000h
0x18000429a  jb      loc_180004210
0x1800042a0  mov     r12, r14
0x1800042a3  mov     [rsp+88h+var_60], r14
0x1800042a8  mov     r13d, 1
0x1800042ae  mov     dword ptr [rsp+88h+var_58], r13d
0x1800042b3  mov     eax, r13d
0x1800042b6  mov     [rsp+88h+var_68], eax
0x1800042ba  mov     dword ptr [rsp+88h+var_58+4], eax
0x1800042be  mov     rdx, r14; struct tagRepairInfo *
0x1800042c1  mov     rcx, [rsp+88h+arg_0]; this
0x1800042c9  call    ?UpdateRepairInfoDescription@CWfHelperClass@@AEAAJPEAUtagRepairInfo@@@Z; CWfHelperClass::UpdateRepairInfoDescription(tagRepairInfo *)
0x1800042ce  mov     ebx, eax
0x1800042d0  test    eax, eax
0x1800042d2  js      short loc_18000430C
0x1800042d4  xor     r12d, r12d
0x1800042d7  xor     r13d, r13d
0x1800042da  xor     eax, eax
0x1800042dc  mov     rcx, [rsp+88h+arg_18]
0x1800042e4  mov     [rcx], r14
0x1800042e7  mov     rcx, [rsp+88h+arg_10]
0x1800042ef  mov     dword ptr [rcx], 1
0x1800042f5  jmp     short loc_180004310
0x1800042f7  mov     ebx, 80070490h
0x1800042fc  mov     edx, 1; unsigned int
0x180004301  mov     r8d, edx; int
0x180004304  mov     rcx, r14; pv
0x180004307  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000430c  mov     eax, [rsp+88h+var_68]
0x180004310  test    r12, r12
0x180004313  jz      short loc_180004323
0x180004315  mov     r8d, eax; int
0x180004318  mov     edx, r13d; unsigned int
0x18000431b  mov     rcx, r12; pv
0x18000431e  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180004323  mov     eax, ebx
0x180004325  mov     rbx, [rsp+88h+arg_8]
0x18000432d  add     rsp, 50h
0x180004331  pop     r15
0x180004333  pop     r14
0x180004335  pop     r13
0x180004337  pop     r12
0x180004339  pop     rdi
0x18000433a  pop     rsi
0x18000433b  pop     rbp
0x18000433c  retn
```
