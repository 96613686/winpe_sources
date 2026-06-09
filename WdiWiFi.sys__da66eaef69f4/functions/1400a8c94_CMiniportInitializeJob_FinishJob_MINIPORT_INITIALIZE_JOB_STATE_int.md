# CMiniportInitializeJob::FinishJob(_MINIPORT_INITIALIZE_JOB_STATE,int)

- ea: `0x1400a8c94`
- end: `0x1400a8d6f`
- name: `?FinishJob@CMiniportInitializeJob@@IEAAXW4_MINIPORT_INITIALIZE_JOB_STATE@@H@Z`
- size: `219`
- prototype: `void __fastcall(CMiniportInitializeJob *__hidden this, enum _MINIPORT_INITIALIZE_JOB_STATE, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140076da0`
- `0x14007c1e0`

## callees

- `0x140004c3c`
- `0x1400a8c94`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x1400a8d4d`
- `NDIS!NdisWriteErrorLogEntry` at `0x1400a8d4d`

## pseudocode

```c
void __fastcall CMiniportInitializeJob::FinishJob(CMiniportInitializeJob *this, int a2, int a3)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  ULONG v9; // edx

  if ( a3 )
  {
    if ( a2 > 5 )
    {
      switch ( a2 )
      {
        case 6:
          v9 = -1073736824;
          goto LABEL_24;
        case 7:
          v9 = -1073736813;
          goto LABEL_24;
        case 8:
          v9 = -1073736815;
          goto LABEL_24;
        case 9:
          v9 = -1073736822;
          goto LABEL_24;
      }
    }
    else
    {
      if ( a2 == 5 )
      {
        v9 = 1073746837;
        goto LABEL_24;
      }
      if ( !a2 )
      {
        v9 = -1073736823;
        goto LABEL_24;
      }
      v6 = a2 - 1;
      if ( !v6 )
      {
        v9 = -1073736821;
        goto LABEL_24;
      }
      v7 = v6 - 1;
      if ( !v7 )
      {
        v9 = -1073736818;
        goto LABEL_24;
      }
      v8 = v7 - 1;
      if ( !v8 )
      {
        v9 = -1073736814;
        goto LABEL_24;
      }
      if ( v8 == 1 )
      {
        v9 = -1073736816;
LABEL_24:
        NdisWriteErrorLogEntry(this->m_pAdapter->m_MiniportAdapterHandle, v9, 2u, a2 | 0x30000u, a3);
        goto LABEL_25;
      }
    }
    v9 = -1073736819;
    goto LABEL_24;
  }
LABEL_25:
  CJobBase::CompleteJob(this, a3);
}

```

## disassembly

```asm
0x1400a8c94  mov     [rsp+arg_0], rbx
0x1400a8c99  push    rdi
0x1400a8c9a  sub     rsp, 30h
0x1400a8c9e  mov     ebx, r8d
0x1400a8ca1  mov     r9d, edx
0x1400a8ca4  mov     rdi, rcx
0x1400a8ca7  test    r8d, r8d
0x1400a8caa  jz      loc_1400A8D59
0x1400a8cb0  cmp     edx, 5
0x1400a8cb3  jg      short loc_1400A8CF9
0x1400a8cb5  jz      short loc_1400A8CF2
0x1400a8cb7  test    edx, edx
0x1400a8cb9  jz      short loc_1400A8CEB
0x1400a8cbb  sub     edx, 1
0x1400a8cbe  jz      short loc_1400A8CE4
0x1400a8cc0  sub     edx, 1
0x1400a8cc3  jz      short loc_1400A8CDD
0x1400a8cc5  sub     edx, 1
0x1400a8cc8  jz      short loc_1400A8CD6
0x1400a8cca  cmp     edx, 1
0x1400a8ccd  jnz     short loc_1400A8D10
0x1400a8ccf  mov     edx, 0C0001390h
0x1400a8cd4  jmp     short loc_1400A8D31
0x1400a8cd6  mov     edx, 0C0001392h
0x1400a8cdb  jmp     short loc_1400A8D31
0x1400a8cdd  mov     edx, 0C000138Eh
0x1400a8ce2  jmp     short loc_1400A8D31
0x1400a8ce4  mov     edx, 0C000138Bh
0x1400a8ce9  jmp     short loc_1400A8D31
0x1400a8ceb  mov     edx, 0C0001389h
0x1400a8cf0  jmp     short loc_1400A8D31
0x1400a8cf2  mov     edx, 40001395h
0x1400a8cf7  jmp     short loc_1400A8D31
0x1400a8cf9  mov     ecx, r9d
0x1400a8cfc  sub     ecx, 6
0x1400a8cff  jz      short loc_1400A8D2C
0x1400a8d01  sub     ecx, 1
0x1400a8d04  jz      short loc_1400A8D25
0x1400a8d06  sub     ecx, 1
0x1400a8d09  jz      short loc_1400A8D1E
0x1400a8d0b  cmp     ecx, 1
0x1400a8d0e  jz      short loc_1400A8D17
0x1400a8d10  mov     edx, 0C000138Dh
0x1400a8d15  jmp     short loc_1400A8D31
0x1400a8d17  mov     edx, 0C000138Ah
0x1400a8d1c  jmp     short loc_1400A8D31
0x1400a8d1e  mov     edx, 0C0001391h
0x1400a8d23  jmp     short loc_1400A8D31
0x1400a8d25  mov     edx, 0C0001393h
0x1400a8d2a  jmp     short loc_1400A8D31
0x1400a8d2c  mov     edx, 0C0001388h; ErrorCode
0x1400a8d31  mov     rcx, [rdi+208h]
0x1400a8d38  or      r9d, 30000h
0x1400a8d3f  mov     r8d, 2; NumberOfErrorValues
0x1400a8d45  mov     [rsp+38h+var_18], ebx
0x1400a8d49  mov     rcx, [rcx+58h]; NdisAdapterHandle
0x1400a8d4d  call    cs:__imp_NdisWriteErrorLogEntry
0x1400a8d54  nop     dword ptr [rax+rax+00h]
0x1400a8d59  mov     edx, ebx; int
0x1400a8d5b  mov     rcx, rdi; this
0x1400a8d5e  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400a8d63  mov     rbx, [rsp+38h+arg_0]
0x1400a8d68  add     rsp, 30h
0x1400a8d6c  pop     rdi
0x1400a8d6d  retn
```
