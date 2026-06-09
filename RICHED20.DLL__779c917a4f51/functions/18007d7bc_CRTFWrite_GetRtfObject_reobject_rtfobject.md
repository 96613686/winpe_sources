# CRTFWrite::GetRtfObject(_reobject &,_rtfobject &)

- ea: `0x18007d7bc`
- end: `0x18007d92f`
- name: `?GetRtfObject@CRTFWrite@@AEAAHAEAU_reobject@@AEAU_rtfobject@@@Z`
- size: `371`
- prototype: `int(CRTFWrite *__hidden this, struct _reobject *, struct _rtfobject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e258`

## callees

- `0x180038bd0`
- `0x180041adc`
- `0x18004a8fc`
- `0x18007d7bc`
- `0x18007d938`
- `0x18008c63c`
- `0x1800907ac`
- `0x18009110a`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18007d893`
- `KERNEL32!GlobalLock` at `0x18007d893`
- `KERNEL32!GlobalUnlock` at `0x18007d8b0`
- `KERNEL32!GlobalUnlock` at `0x18007d8b0`
- `GDI32!DeleteMetaFile` at `0x18007d8a7`
- `GDI32!DeleteMetaFile` at `0x18007d8a7`

## string_xrefs

- `0x18007d82a`: `ProgIDFromCLSID`

## pseudocode

```c
__int64 __fastcall CRTFWrite::GetRtfObject(CRTFWrite *this, struct _reobject *a2, struct _rtfobject *a3)
{
  DWORD dwFlags; // ebp
  int v6; // ebp
  struct tagDVTARGETDEVICE *v7; // r9
  unsigned int RtfObjectMetafilePict; // r15d
  int v9; // esi
  struct COLE32_PROC *Ole32Procs; // rax
  unsigned int (__fastcall **v11)(CLSID *, __int64 *); // r14
  void *MetafilePictFromOleObject; // rax
  CRTFWrite *v13; // rcx
  void *v14; // rbx
  LPVOID v15; // rax
  HMETAFILE v16; // rcx
  LONG cx; // ecx
  struct tagSIZE sizel; // [rsp+50h] [rbp+8h] BYREF
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  sizel = (struct tagSIZE)this;
  dwFlags = a2->dwFlags;
  sizel = a2->sizel;
  v20 = 0;
  v6 = dwFlags & 0x40000000;
  memset_0(a3, 0, 0x60u);
  if ( !a2->pstg )
    return 0;
  RtfObjectMetafilePict = 0;
  v9 = 0;
  if ( !v6 )
  {
    Ole32Procs = CThreadData::GetOle32Procs();
    v11 = (unsigned int (__fastcall **)(CLSID *, __int64 *))((char *)Ole32Procs + 40);
    if ( !*((_QWORD *)Ole32Procs + 5) )
      SetProcAddr((char *)Ole32Procs + 40, 1, "ProgIDFromCLSID");
    if ( !*v11 || (*v11)(&a2->clsid, &v20) )
      v9 = 1;
    else
      *((_QWORD *)a3 + 7) = v20;
  }
  MetafilePictFromOleObject = OleStdGetMetafilePictFromOleObject(a2->poleobj, a2->dvaspect, &sizel, v7);
  v14 = MetafilePictFromOleObject;
  if ( MetafilePictFromOleObject )
  {
    RtfObjectMetafilePict = CRTFWrite::GetRtfObjectMetafilePict(v13, MetafilePictFromOleObject, a3, &sizel);
    v15 = GlobalLock(v14);
    if ( v15 )
    {
      v16 = (HMETAFILE)*((_QWORD *)v15 + 2);
      if ( v16 )
        DeleteMetaFile(v16);
      GlobalUnlock(v14);
    }
    CW32System::GlobalFree(v14);
    if ( !RtfObjectMetafilePict )
    {
      if ( v9 )
        return 0;
    }
  }
  if ( !v6 )
  {
    cx = sizel.cx;
    *(_WORD *)a3 = 2 * (v9 ^ 1) + 1;
    *((_DWORD *)a3 + 4) = (__int16)CW32System::MulDiv(cx, 72, 127);
    RtfObjectMetafilePict = 1;
    *((_DWORD *)a3 + 5) = (__int16)CW32System::MulDiv(sizel.cy, 72, 127);
  }
  *((_DWORD *)a3 + 3) = 0;
  return RtfObjectMetafilePict;
}

```

## disassembly

```asm
0x18007d7bc  mov     r11, rsp
0x18007d7bf  mov     [r11+18h], rbx
0x18007d7c3  mov     [r11+20h], rbp
0x18007d7c7  mov     [r11+8], rcx
0x18007d7cb  push    rsi
0x18007d7cc  push    rdi
0x18007d7cd  push    r13
0x18007d7cf  push    r14
0x18007d7d1  push    r15
0x18007d7d3  sub     rsp, 20h
0x18007d7d7  mov     ebp, [rdx+3Ch]
0x18007d7da  mov     rdi, r8
0x18007d7dd  mov     rax, [rdx+30h]
0x18007d7e1  mov     rbx, rdx
0x18007d7e4  xor     edx, edx; Val
0x18007d7e6  mov     [r11+8], rax
0x18007d7ea  mov     rcx, rdi; void *
0x18007d7ed  mov     qword ptr [r11+10h], 0
0x18007d7f5  and     ebp, 40000000h
0x18007d7fb  lea     r8d, [rdx+60h]; Size
0x18007d7ff  call    memset_0
0x18007d804  cmp     qword ptr [rbx+20h], 0
0x18007d809  jz      loc_18007D916
0x18007d80f  xor     r15d, r15d
0x18007d812  xor     esi, esi
0x18007d814  lea     r13d, [r15+1]
0x18007d818  test    ebp, ebp
0x18007d81a  jnz     short loc_18007D864
0x18007d81c  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007d821  lea     r14, [rax+28h]
0x18007d825  cmp     [r14], rsi
0x18007d828  jnz     short loc_18007D83C
0x18007d82a  lea     r8, aProgidfromclsi; "ProgIDFromCLSID"
0x18007d831  mov     edx, r13d
0x18007d834  mov     rcx, r14
0x18007d837  call    SetProcAddr
0x18007d83c  mov     rax, [r14]
0x18007d83f  test    rax, rax
0x18007d842  jz      short loc_18007D861
0x18007d844  lea     rcx, [rbx+8]
0x18007d848  lea     rdx, [rsp+48h+arg_8]
0x18007d84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d852  test    eax, eax
0x18007d854  jnz     short loc_18007D861
0x18007d856  mov     rax, [rsp+48h+arg_8]
0x18007d85b  mov     [rdi+38h], rax
0x18007d85f  jmp     short loc_18007D864
0x18007d861  mov     esi, r13d
0x18007d864  mov     edx, [rbx+38h]; unsigned int
0x18007d867  lea     r8, [rsp+48h+arg_0]; struct tagSIZE *
0x18007d86c  mov     rcx, [rbx+18h]; struct IOleObject *
0x18007d870  call    ?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@KPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@@Z; OleStdGetMetafilePictFromOleObject(IOleObject *,ulong,tagSIZE *,tagDVTARGETDEVICE *)
0x18007d875  mov     rbx, rax
0x18007d878  test    rax, rax
0x18007d87b  jz      short loc_18007D8C7
0x18007d87d  lea     r9, [rsp+48h+arg_0]; struct tagSIZE *
0x18007d882  mov     r8, rdi; struct _rtfobject *
0x18007d885  mov     rdx, rax; void *
0x18007d888  call    ?GetRtfObjectMetafilePict@CRTFWrite@@AEAAHPEAXAEAU_rtfobject@@AEAUtagSIZE@@@Z; CRTFWrite::GetRtfObjectMetafilePict(void *,_rtfobject &,tagSIZE &)
0x18007d88d  mov     rcx, rbx; hMem
0x18007d890  mov     r15d, eax
0x18007d893  call    cs:__imp_GlobalLock
0x18007d899  test    rax, rax
0x18007d89c  jz      short loc_18007D8B6
0x18007d89e  mov     rcx, [rax+10h]; hmf
0x18007d8a2  test    rcx, rcx
0x18007d8a5  jz      short loc_18007D8AD
0x18007d8a7  call    cs:__imp_DeleteMetaFile
0x18007d8ad  mov     rcx, rbx; hMem
0x18007d8b0  call    cs:__imp_GlobalUnlock
0x18007d8b6  mov     rcx, rbx; void *
0x18007d8b9  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007d8be  test    r15d, r15d
0x18007d8c1  jnz     short loc_18007D8C7
0x18007d8c3  test    esi, esi
0x18007d8c5  jnz     short loc_18007D916
0x18007d8c7  test    ebp, ebp
0x18007d8c9  jnz     short loc_18007D90A
0x18007d8cb  mov     ecx, [rsp+48h+arg_0.cx]; int
0x18007d8cf  lea     ebx, [rbp+48h]
0x18007d8d2  xor     si, r13w
0x18007d8d6  mov     edx, ebx; int
0x18007d8d8  add     si, si
0x18007d8db  add     si, r13w
0x18007d8df  mov     [rdi], si
0x18007d8e2  lea     esi, [rbp+7Fh]
0x18007d8e5  mov     r8d, esi; int
0x18007d8e8  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007d8ed  movsx   ecx, ax
0x18007d8f0  mov     r8d, esi; int
0x18007d8f3  mov     [rdi+10h], ecx
0x18007d8f6  mov     edx, ebx; int
0x18007d8f8  mov     ecx, [rsp+48h+arg_0.cy]; int
0x18007d8fc  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007d901  movsx   ecx, ax
0x18007d904  mov     r15d, r13d
0x18007d907  mov     [rdi+14h], ecx
0x18007d90a  mov     dword ptr [rdi+0Ch], 0
0x18007d911  mov     eax, r15d
0x18007d914  jmp     short loc_18007D918
0x18007d916  xor     eax, eax
0x18007d918  mov     rbx, [rsp+48h+arg_10]
0x18007d91d  mov     rbp, [rsp+48h+arg_18]
0x18007d922  add     rsp, 20h
0x18007d926  pop     r15
0x18007d928  pop     r14
0x18007d92a  pop     r13
0x18007d92c  pop     rdi
0x18007d92d  pop     rsi
0x18007d92e  retn
```
