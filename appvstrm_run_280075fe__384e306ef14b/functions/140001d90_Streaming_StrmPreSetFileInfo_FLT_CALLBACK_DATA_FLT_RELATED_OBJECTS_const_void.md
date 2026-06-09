# Streaming::StrmPreSetFileInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140001d90`
- end: `0x140001de9`
- name: `?StrmPreSetFileInfo@Streaming@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `89`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x140001d90`
- `0x140013160`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPreSetFileInfo(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        void **a4)
{
  struct _FILE_OBJECT *Information; // r10
  unsigned __int64 v6; // rcx

  if ( !this )
    return 1;
  if ( !a2 )
    return 1;
  Information = (struct _FILE_OBJECT *)a2->IoStatus.Information;
  if ( !Information )
    return 1;
  v6 = this->Iopb->Parameters.Create.Options - 10;
  if ( (_DWORD)v6
    && (v6 = (unsigned int)(v6 - 1), (_DWORD)v6)
    && (v6 = (unsigned int)(v6 - 8), (_DWORD)v6)
    && (v6 = (unsigned int)(v6 - 1), (_DWORD)v6)
    && (v6 = (unsigned int)(v6 - 19), (_DWORD)v6)
    && (_DWORD)v6 != 26 )
  {
    return 1;
  }
  else
  {
    return Streaming::StrmFltInterface::WriteFile(
             (Streaming::StrmFltInterface *)v6,
             (struct _FLT_INSTANCE *)a2->IoStatus.Pointer,
             Information,
             this);
  }
}

```

## disassembly

```asm
0x140001d90  sub     rsp, 28h
0x140001d94  mov     r9, rcx; struct _FLT_CALLBACK_DATA *
0x140001d97  test    rcx, rcx
0x140001d9a  jz      short loc_140001DDE
0x140001d9c  test    rdx, rdx
0x140001d9f  jz      short loc_140001DDE
0x140001da1  mov     r10, [rdx+20h]
0x140001da5  test    r10, r10
0x140001da8  jz      short loc_140001DDE
0x140001daa  mov     r8, [rcx+10h]
0x140001dae  mov     ecx, [r8+20h]
0x140001db2  sub     ecx, 0Ah
0x140001db5  jz      short loc_140001DD0
0x140001db7  sub     ecx, 1
0x140001dba  jz      short loc_140001DD0
0x140001dbc  sub     ecx, 8
0x140001dbf  jz      short loc_140001DD0
0x140001dc1  sub     ecx, 1
0x140001dc4  jz      short loc_140001DD0
0x140001dc6  sub     ecx, 13h; this
0x140001dc9  jz      short loc_140001DD0
0x140001dcb  cmp     ecx, 1Ah
0x140001dce  jnz     short loc_140001DDE
0x140001dd0  mov     rdx, [rdx+18h]; struct _FLT_INSTANCE *
0x140001dd4  mov     r8, r10; struct _FILE_OBJECT *
0x140001dd7  call    ?WriteFile@StrmFltInterface@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@@Z; Streaming::StrmFltInterface::WriteFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &)
0x140001ddc  jmp     short loc_140001DE3
0x140001dde  mov     eax, 1
0x140001de3  add     rsp, 28h
0x140001de7  retn
```
