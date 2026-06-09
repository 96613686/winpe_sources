# CILogRead::DumpPage(char *,ulong,ulong,_DUMP_TYPE,ulong *)

- ea: `0x180002900`
- end: `0x180002a88`
- name: `?DumpPage@CILogRead@@UEAAJPEADKKW4_DUMP_TYPE@@PEAK@Z`
- size: `392`
- prototype: `int __high(char *, unsigned int, unsigned int, enum _DUMP_TYPE, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002900`
- `0x18000341c`
- `0x180003a5c`
- `0x180005b64`
- `0x18000b974`
- `0x18000c6b8`
- `0x18000c7fc`
- `0x18001280a`

## pseudocode

```c
__int64 __fastcall CILogRead::DumpPage(__int64 a1, void *a2, unsigned int a3, unsigned int a4, int a5, _DWORD *a6)
{
  __int64 result; // rax
  int v11; // edx
  ulong v12; // r9d
  LPCVOID *v13; // rsi
  int *v14; // rax
  ulong restarted; // ebx
  struct _RECORDPAGE *FirstPage; // rax
  unsigned int v17; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+44h] [rbp-24h] BYREF
  ulong v19; // [rsp+48h] [rbp-20h] BYREF
  ulong v20; // [rsp+4Ch] [rbp-1Ch] BYREF
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF

  v21 = 0;
  if ( a2 )
  {
    if ( a3 >= 0xA230 )
    {
      memset_0(a2, 0, 0xA230u);
      try
      {
        result = (__int64)CLogStorage::_MapBuffer(
                            *(CLogStorage **)(*(_QWORD *)(a1 + 16) + 392LL),
                            a4 * *(_DWORD *)(*(_QWORD *)(a1 + 16) + 632LL),
                            *(_DWORD *)(*(_QWORD *)(a1 + 16) + 632LL),
                            1,
                            0);
      }
      catch ( long v19 )
      {
        return v19;
      }
      catch ( ulong v20 )
      {
        return v20;
      }
      v13 = (LPCVOID *)result;
      if ( result )
      {
        if ( a4 >= 2 )
        {
          FirstPage = CBuffer::GetFirstPage((CBuffer *)result, v11, 0, &v17, &v21);
          restarted = CILogRead::_DumpDataPage(a1, (char *)a2, a3, a4, FirstPage, a5, a6, v21);
        }
        else
        {
          v14 = (int *)CLogStorage::_VerifyRestart(
                         *(CLogStorage **)(*(_QWORD *)(a1 + 16) + 392LL),
                         (struct CBuffer *)result,
                         &v17,
                         v12,
                         &v18,
                         &v21);
          restarted = CILogRead::_DumpRestartPage(a1, (char *)a2, a3, a4, v14, a5, a6, v21);
        }
        CLogStorage::_UnmapBuffer(*(CLogStorage **)(*(_QWORD *)(a1 + 16) + 392LL), v13, 0);
        return restarted;
      }
    }
    else
    {
      return 2147942487LL;
    }
  }
  else
  {
    if ( a6 )
      *a6 = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002900  mov     [rsp+arg_0], rbx
0x180002905  mov     [rsp+arg_10], rsi
0x18000290a  push    rdi
0x18000290b  push    r14
0x18000290d  push    r15
0x18000290f  sub     rsp, 50h
0x180002913  mov     r14d, r9d
0x180002916  mov     r15d, r8d
0x180002919  mov     rbx, rdx
0x18000291c  mov     rdi, rcx
0x18000291f  mov     [rsp+68h+arg_8], 0
0x180002927  test    rdx, rdx
0x18000292a  jnz     short loc_180002942
0x18000292c  mov     rax, [rsp+68h+arg_28]
0x180002934  test    rax, rax
0x180002937  jz      short loc_18000293B
0x180002939  mov     [rax], edx
0x18000293b  xor     eax, eax
0x18000293d  jmp     loc_180002A71
0x180002942  mov     r8d, 0A230h; Size
0x180002948  cmp     r15d, r8d
0x18000294b  jnb     short loc_180002957
0x18000294d  mov     eax, 80070057h
0x180002952  jmp     loc_180002A71
0x180002957  xor     edx, edx; Val
0x180002959  mov     rcx, rbx; void *
0x18000295c  call    memset_0
0x180002961  mov     rcx, [rdi+10h]
0x180002965  mov     r8d, [rcx+278h]; unsigned int
0x18000296c  mov     edx, r8d
0x18000296f  imul    edx, r14d; unsigned int
0x180002973  mov     dword ptr [rsp+68h+var_48], 0; unsigned int
0x18000297b  mov     r9d, 1; int
0x180002981  mov     rcx, [rcx+188h]; this
0x180002988  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000298d  mov     rsi, rax
0x180002990  test    rax, rax
0x180002993  jz      loc_180002A71
0x180002999  lea     rax, [rsp+68h+arg_8]
0x18000299e  cmp     r14d, 2
0x1800029a2  jnb     short loc_180002A05
0x1800029a4  mov     rcx, [rdi+10h]
0x1800029a8  mov     [rsp+68h+var_40], rax; unsigned int *
0x1800029ad  lea     rax, [rsp+68h+var_24]
0x1800029b2  mov     [rsp+68h+var_48], rax; int *
0x1800029b7  lea     r8, [rsp+68h+var_28]; unsigned int *
0x1800029bc  mov     rdx, rsi; struct CBuffer *
0x1800029bf  mov     rcx, [rcx+188h]; this
0x1800029c6  call    ?_VerifyRestart@CLogStorage@@AEAAPEAU_RESTARTPAGE@@PEAVCBuffer@@PEAKKPEAH1@Z; CLogStorage::_VerifyRestart(CBuffer *,ulong *,ulong,int *,ulong *)
0x1800029cb  mov     ecx, [rsp+68h+arg_8]
0x1800029cf  mov     [rsp+68h+var_30], ecx
0x1800029d3  mov     rcx, [rsp+68h+arg_28]
0x1800029db  mov     [rsp+68h+var_38], rcx
0x1800029e0  mov     ecx, [rsp+68h+arg_20]
0x1800029e7  mov     dword ptr [rsp+68h+var_40], ecx
0x1800029eb  mov     [rsp+68h+var_48], rax
0x1800029f0  mov     r9d, r14d
0x1800029f3  mov     r8d, r15d
0x1800029f6  mov     rdx, rbx
0x1800029f9  mov     rcx, rdi
0x1800029fc  call    ?_DumpRestartPage@CILogRead@@AEAAJPEADKKPEAU_RESTARTPAGE@@W4_DUMP_TYPE@@PEAKK@Z; CILogRead::_DumpRestartPage(char *,ulong,ulong,_RESTARTPAGE *,_DUMP_TYPE,ulong *,ulong)
0x180002a01  mov     ebx, eax
0x180002a03  jmp     short loc_180002A52
0x180002a05  mov     [rsp+68h+var_48], rax; unsigned int *
0x180002a0a  lea     r9, [rsp+68h+var_28]; unsigned int *
0x180002a0f  xor     r8d, r8d; unsigned int
0x180002a12  mov     rcx, rsi; this
0x180002a15  call    ?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z; CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)
0x180002a1a  mov     ecx, [rsp+68h+arg_8]
0x180002a1e  mov     [rsp+68h+var_30], ecx
0x180002a22  mov     rcx, [rsp+68h+arg_28]
0x180002a2a  mov     [rsp+68h+var_38], rcx
0x180002a2f  mov     ecx, [rsp+68h+arg_20]
0x180002a36  mov     dword ptr [rsp+68h+var_40], ecx
0x180002a3a  mov     [rsp+68h+var_48], rax
0x180002a3f  mov     r9d, r14d
0x180002a42  mov     r8d, r15d
0x180002a45  mov     rdx, rbx
0x180002a48  mov     rcx, rdi
0x180002a4b  call    ?_DumpDataPage@CILogRead@@AEAAJPEADKKPEAU_RECORDPAGE@@W4_DUMP_TYPE@@PEAKK@Z; CILogRead::_DumpDataPage(char *,ulong,ulong,_RECORDPAGE *,_DUMP_TYPE,ulong *,ulong)
0x180002a50  mov     ebx, eax
0x180002a52  mov     rcx, [rdi+10h]
0x180002a56  xor     r8d, r8d; int
0x180002a59  mov     rdx, rsi; struct CBuffer *
0x180002a5c  mov     rcx, [rcx+188h]; this
0x180002a63  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x180002a68  nop
0x180002a69  jmp     short loc_180002A6F
0x180002a6b  mov     ebx, [rsp+68h+arg_8]
0x180002a6f  mov     eax, ebx
0x180002a71  lea     r11, [rsp+68h+var_18]
0x180002a76  mov     rbx, [r11+20h]
0x180002a7a  mov     rsi, [r11+30h]
0x180002a7e  mov     rsp, r11
0x180002a81  pop     r15
0x180002a83  pop     r14
0x180002a85  pop     rdi
0x180002a86  retn
```
