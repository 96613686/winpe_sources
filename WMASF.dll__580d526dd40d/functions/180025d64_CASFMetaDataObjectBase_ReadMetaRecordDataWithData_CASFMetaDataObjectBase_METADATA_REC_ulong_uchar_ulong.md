# CASFMetaDataObjectBase::ReadMetaRecordDataWithData(CASFMetaDataObjectBase::METADATA_REC *,ulong,uchar *,ulong *)

- ea: `0x180025d64`
- end: `0x180025e42`
- name: `?ReadMetaRecordDataWithData@CASFMetaDataObjectBase@@IEAAJPEAUMETADATA_REC@1@KPEAEPEAK@Z`
- size: `222`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *this, struct CASFMetaDataObjectBase::METADATA_REC *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180025d30`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x180009dd8`
- `0x180025d64`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::ReadMetaRecordDataWithData(
        CASFMetaDataObjectBase *this,
        struct CASFMetaDataObjectBase::METADATA_REC *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  unsigned int *v5; // rdi
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // ebp
  __int64 result; // rax
  void *v12; // rax
  unsigned __int64 v13; // rax
  CASFMetaDataObjectBase *v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = this;
  v5 = a5;
  if ( !a5 || !a2 || a3 && !a4 )
    return 2147942487LL;
  v8 = *((_DWORD *)a2 + 4);
  LODWORD(v14) = 0;
  v10 = CHECK_FOR_SPACE((unsigned int *)&v14, v8, a3);
  result = 3222079441LL;
  if ( v10 == -1072887855 )
    return result;
  *((_QWORD *)a2 + 3) = 0;
  v12 = operator new[](v9);
  *((_QWORD *)a2 + 3) = v12;
  if ( !v12 )
    return 2147942414LL;
  memcpy_0(v12, a4, *((unsigned int *)a2 + 4));
  if ( ((*((_DWORD *)a2 + 1) - 1) & 0xFFFF7FFF) == 0 )
  {
    v13 = *((unsigned int *)a2 + 4);
    if ( (v13 & 1) != 0 )
    {
      operator delete(*((void **)a2 + 3));
      result = 3222079458LL;
      *((_QWORD *)a2 + 3) = 0;
      return result;
    }
    if ( (_DWORD)v13 )
      *(_WORD *)(*((_QWORD *)a2 + 3) + 2 * (v13 >> 1) - 2) = 0;
  }
  *v5 = (unsigned int)v14;
  return v10;
}

```

## disassembly

```asm
0x180025d64  mov     [rsp+arg_0], rcx
0x180025d69  push    rbx
0x180025d6a  push    rbp
0x180025d6b  push    rsi
0x180025d6c  push    rdi
0x180025d6d  sub     rsp, 28h
0x180025d71  mov     rdi, [rsp+48h+arg_20]
0x180025d76  mov     rsi, r9
0x180025d79  mov     rbx, rdx
0x180025d7c  test    rdi, rdi
0x180025d7f  jz      loc_180025E34
0x180025d85  test    rdx, rdx
0x180025d88  jz      loc_180025E34
0x180025d8e  test    r8d, r8d
0x180025d91  jz      short loc_180025D9C
0x180025d93  test    r9, r9
0x180025d96  jz      loc_180025E34
0x180025d9c  mov     edx, [rdx+10h]; unsigned int
0x180025d9f  lea     rcx, [rsp+48h+arg_0]; unsigned int *
0x180025da4  mov     dword ptr [rsp+48h+arg_0], 0
0x180025dac  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x180025db1  mov     ebp, eax
0x180025db3  mov     eax, 0C00D07D1h
0x180025db8  cmp     ebp, eax
0x180025dba  jz      short loc_180025E39
0x180025dbc  mov     ecx, edx; unsigned __int64
0x180025dbe  mov     qword ptr [rbx+18h], 0
0x180025dc6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025dcb  mov     [rbx+18h], rax
0x180025dcf  test    rax, rax
0x180025dd2  jnz     short loc_180025DDB
0x180025dd4  mov     eax, 8007000Eh
0x180025dd9  jmp     short loc_180025E39
0x180025ddb  mov     r8d, [rbx+10h]; Size
0x180025ddf  mov     rdx, rsi; Src
0x180025de2  mov     rcx, rax; void *
0x180025de5  call    memcpy_0
0x180025dea  mov     eax, [rbx+4]
0x180025ded  dec     eax
0x180025def  test    eax, 0FFFF7FFFh
0x180025df4  jnz     short loc_180025E2A
0x180025df6  mov     eax, [rbx+10h]
0x180025df9  test    al, 1
0x180025dfb  jz      short loc_180025E15
0x180025dfd  mov     rcx, [rbx+18h]; Block
0x180025e01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025e06  mov     eax, 0C00D07E2h
0x180025e0b  mov     qword ptr [rbx+18h], 0
0x180025e13  jmp     short loc_180025E39
0x180025e15  test    eax, eax
0x180025e17  jz      short loc_180025E2A
0x180025e19  mov     rcx, [rbx+18h]
0x180025e1d  mov     rdx, rax
0x180025e20  shr     rdx, 1
0x180025e23  xor     eax, eax
0x180025e25  mov     [rcx+rdx*2-2], ax
0x180025e2a  mov     eax, dword ptr [rsp+48h+arg_0]
0x180025e2e  mov     [rdi], eax
0x180025e30  mov     eax, ebp
0x180025e32  jmp     short loc_180025E39
0x180025e34  mov     eax, 80070057h
0x180025e39  add     rsp, 28h
0x180025e3d  pop     rdi
0x180025e3e  pop     rsi
0x180025e3f  pop     rbp
0x180025e40  pop     rbx
0x180025e41  retn
```
