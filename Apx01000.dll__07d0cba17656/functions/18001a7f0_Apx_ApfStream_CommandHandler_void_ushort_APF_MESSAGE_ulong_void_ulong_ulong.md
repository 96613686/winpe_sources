# Apx::ApfStream::_CommandHandler(void *,ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)

- ea: `0x18001a7f0`
- end: `0x18001a8b5`
- name: `?_CommandHandler@ApfStream@Apx@@KAJPEAXGPEAUAPF_MESSAGE@@K0KPEAK@Z`
- size: `197`
- prototype: `__int64 __fastcall(Apx::ApfStream *this, __int16, struct APF_MESSAGE *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a12c`
- `0x18001a70c`
- `0x18001a7f0`

## pseudocode

```c
__int64 __fastcall Apx::ApfStream::_CommandHandler(
        Apx::ApfStream *this,
        __int16 a2,
        struct APF_MESSAGE *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int16 v11; // dx
  unsigned int v12; // ebx
  void *v14; // [rsp+20h] [rbp-48h]
  unsigned int v15; // [rsp+28h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5d5e8d85d725375cf011861eaabc6f3c_Traceguids);
  }
  v11 = *((_WORD *)a3 + 13);
  *a7 = 0;
  if ( a2 == 2 )
  {
    v12 = Apx::ApfStream::StreamHandler(this, v11, a3, a4, v14, v15, a7);
  }
  else
  {
    v12 = -1073741637;
    if ( a2 != 4 )
      v12 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5d5e8d85d725375cf011861eaabc6f3c_Traceguids);
  }
  return v12;
}

```

## disassembly

```asm
0x18001a7f0  push    rbx
0x18001a7f2  push    rbp
0x18001a7f3  push    rsi
0x18001a7f4  push    rdi
0x18001a7f5  push    r14
0x18001a7f7  sub     rsp, 40h
0x18001a7fb  mov     esi, r9d
0x18001a7fe  mov     rbx, r8
0x18001a801  movzx   edi, dx
0x18001a804  mov     rbp, rcx
0x18001a807  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a80e  lea     r14, WPP_GLOBAL_Control
0x18001a815  cmp     rcx, r14
0x18001a818  jz      short loc_18001A83B
0x18001a81a  test    byte ptr [rcx+1Ch], 1
0x18001a81e  jz      short loc_18001A83B
0x18001a820  cmp     byte ptr [rcx+19h], 5
0x18001a824  jb      short loc_18001A83B
0x18001a826  mov     rcx, [rcx+10h]
0x18001a82a  lea     r8, WPP_5d5e8d85d725375cf011861eaabc6f3c_Traceguids
0x18001a831  mov     edx, 0Ah
0x18001a836  call    WPP_SF_
0x18001a83b  mov     rax, [rsp+68h+arg_30]
0x18001a843  movzx   edx, word ptr [rbx+1Ah]; unsigned __int16
0x18001a847  mov     dword ptr [rax], 0
0x18001a84d  cmp     di, 2
0x18001a851  jz      short loc_18001A866
0x18001a853  cmp     di, 4
0x18001a857  mov     ebx, 0C00000BBh
0x18001a85c  mov     eax, 0C000000Dh
0x18001a861  cmovnz  ebx, eax
0x18001a864  jmp     short loc_18001A87B
0x18001a866  mov     r9d, esi; unsigned int
0x18001a869  mov     [rsp+68h+var_38], rax; unsigned int *
0x18001a86e  mov     r8, rbx; struct APF_MESSAGE *
0x18001a871  mov     rcx, rbp; this
0x18001a874  call    ?StreamHandler@ApfStream@Apx@@IEAAJGPEAUAPF_MESSAGE@@KPEAXKPEAK@Z; Apx::ApfStream::StreamHandler(ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)
0x18001a879  mov     ebx, eax
0x18001a87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a882  cmp     rcx, r14
0x18001a885  jz      short loc_18001A8A8
0x18001a887  test    byte ptr [rcx+1Ch], 1
0x18001a88b  jz      short loc_18001A8A8
0x18001a88d  cmp     byte ptr [rcx+19h], 5
0x18001a891  jb      short loc_18001A8A8
0x18001a893  mov     rcx, [rcx+10h]
0x18001a897  lea     r8, WPP_5d5e8d85d725375cf011861eaabc6f3c_Traceguids
0x18001a89e  mov     edx, 0Bh
0x18001a8a3  call    WPP_SF_
0x18001a8a8  mov     eax, ebx
0x18001a8aa  add     rsp, 40h
0x18001a8ae  pop     r14
0x18001a8b0  pop     rdi
0x18001a8b1  pop     rsi
0x18001a8b2  pop     rbp
0x18001a8b3  pop     rbx
0x18001a8b4  retn
```
