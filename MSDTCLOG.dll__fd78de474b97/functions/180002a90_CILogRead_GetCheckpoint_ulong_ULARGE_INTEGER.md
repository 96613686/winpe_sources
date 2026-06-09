# CILogRead::GetCheckpoint(ulong,_ULARGE_INTEGER *)

- ea: `0x180002a90`
- end: `0x180002b16`
- name: `?GetCheckpoint@CILogRead@@UEAAJKPEAT_ULARGE_INTEGER@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CILogRead *__hidden this, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002a90`
- `0x180004708`

## pseudocode

```c
__int64 __fastcall CILogRead::GetCheckpoint(CILogRead *this, unsigned int a2, union _ULARGE_INTEGER *a3)
{
  struct _STRMTBL *Stream; // rax
  unsigned int v6; // r8d
  __int64 v7; // rcx
  ULONGLONG v8; // rax

  if ( !a3 || a2 > 2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 1) )
    return 2147549183LL;
  a3->QuadPart = 0;
  Stream = CILogStorage::GetStream(
             (CILogStorage *)(*((_QWORD *)this + 2) + 96LL),
             *(_DWORD *)(*((_QWORD *)this + 1) + 328LL));
  if ( !Stream )
    return 2147549183LL;
  v6 = *((unsigned __int16 *)Stream + 9) - a2;
  v7 = v6 + 2;
  if ( a2 <= *((unsigned __int16 *)Stream + 9) )
    v7 = v6;
  v8 = *(_QWORD *)((char *)Stream + 8 * v7 + 28);
  if ( !v8 )
    return 2147500037LL;
  a3->QuadPart = v8;
  return 0;
}

```

## disassembly

```asm
0x180002a90  mov     [rsp+arg_0], rbx
0x180002a95  push    rdi
0x180002a96  sub     rsp, 20h
0x180002a9a  mov     rbx, r8
0x180002a9d  mov     edi, edx
0x180002a9f  test    r8, r8
0x180002aa2  jz      short loc_180002B06
0x180002aa4  cmp     edx, 2
0x180002aa7  ja      short loc_180002B06
0x180002aa9  cmp     qword ptr [rcx+8], 0
0x180002aae  jz      short loc_180002AFF
0x180002ab0  mov     qword ptr [r8], 0
0x180002ab7  mov     rdx, [rcx+8]
0x180002abb  mov     rcx, [rcx+10h]
0x180002abf  add     rcx, 60h ; '`'; this
0x180002ac3  mov     edx, [rdx+148h]; unsigned int
0x180002ac9  call    ?GetStream@CILogStorage@@AEAAPEAU_STRMTBL@@K@Z; CILogStorage::GetStream(ulong)
0x180002ace  test    rax, rax
0x180002ad1  jz      short loc_180002AFF
0x180002ad3  movzx   edx, word ptr [rax+12h]
0x180002ad7  mov     r8d, edx
0x180002ada  sub     r8d, edi
0x180002add  cmp     edi, edx
0x180002adf  lea     ecx, [r8+2]
0x180002ae3  cmovbe  ecx, r8d
0x180002ae7  mov     rax, [rax+rcx*8+1Ch]
0x180002aec  test    rax, rax
0x180002aef  jnz     short loc_180002AF8
0x180002af1  mov     eax, 80004005h
0x180002af6  jmp     short loc_180002B0B
0x180002af8  mov     [rbx], rax
0x180002afb  xor     eax, eax
0x180002afd  jmp     short loc_180002B0B
0x180002aff  mov     eax, 8000FFFFh
0x180002b04  jmp     short loc_180002B0B
0x180002b06  mov     eax, 80070057h
0x180002b0b  mov     rbx, [rsp+28h+arg_0]
0x180002b10  add     rsp, 20h
0x180002b14  pop     rdi
0x180002b15  retn
```
