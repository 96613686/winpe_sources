# SBC::ConfigEncode(SBC_CONFIG const &,bool)

- ea: `0x140018094`
- end: `0x14001813f`
- name: `?ConfigEncode@SBC@@QEAAJAEBUSBC_CONFIG@@_N@Z`
- size: `171`
- prototype: `int(SBC *__hidden this, const struct SBC_CONFIG *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018740`

## callees

- `0x140017f88`
- `0x140018094`
- `0x140018634`
- `0x14001b2c0`

## pseudocode

```c
__int64 __fastcall SBC::ConfigEncode(SBC *this, const struct SBC_CONFIG *a2)
{
  unsigned int v2; // edi
  SBC::SbcControl *v4; // r11
  int v5; // r9d
  int v6; // edx
  int v7; // r8d
  int v8; // eax
  __int64 v9; // r11

  v2 = 0;
  *((_QWORD *)this + 8) = 0;
  if ( SBC::IsConfigValid(a2) )
  {
    *((_DWORD *)v4 + 3) = *((_DWORD *)a2 + 5);
    *((_DWORD *)v4 + 8) = *((_DWORD *)a2 + 6);
    v5 = *((_DWORD *)a2 + 1);
    *((_DWORD *)v4 + 6) = v5;
    *((_DWORD *)v4 + 2) = *((_DWORD *)a2 + 3);
    v6 = *((_DWORD *)a2 + 4);
    *((_DWORD *)v4 + 5) = v6;
    *((_DWORD *)v4 + 1) = *(_DWORD *)a2;
    v7 = *((_DWORD *)a2 + 2);
    *((_DWORD *)v4 + 7) = v7;
    *(_DWORD *)v4 = *((_BYTE *)a2 + 28) != 0 ? 173 : 156;
    *((_DWORD *)v4 + 16) = 2 * v5 * v6 * v7;
    v8 = SBC::SbcControl::CalculateSbcFrameLength(v4);
    *(_DWORD *)(v9 + 68) = v8;
    memset((void *)(v9 + 3304), 0, 0x140u);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v2;
}

```

## disassembly

```asm
0x140018094  mov     [rsp+arg_0], rbx
0x140018099  push    rdi
0x14001809a  sub     rsp, 20h
0x14001809e  mov     r11, rcx
0x1400180a1  xor     edi, edi
0x1400180a3  mov     [rcx+40h], rdi
0x1400180a7  mov     rbx, rdx
0x1400180aa  mov     rcx, rdx; struct SBC_CONFIG *
0x1400180ad  call    ?IsConfigValid@SBC@@SA_NAEBUSBC_CONFIG@@@Z; SBC::IsConfigValid(SBC_CONFIG const &)
0x1400180b2  test    al, al
0x1400180b4  jnz     short loc_1400180BD
0x1400180b6  mov     edi, 0C000000Dh
0x1400180bb  jmp     short loc_140018131
0x1400180bd  mov     eax, [rbx+14h]
0x1400180c0  mov     [r11+0Ch], eax
0x1400180c4  mov     eax, [rbx+18h]
0x1400180c7  mov     [r11+20h], eax
0x1400180cb  mov     r9d, [rbx+4]
0x1400180cf  mov     [r11+18h], r9d
0x1400180d3  mov     eax, [rbx+0Ch]
0x1400180d6  mov     [r11+8], eax
0x1400180da  mov     edx, [rbx+10h]
0x1400180dd  mov     [r11+14h], edx
0x1400180e1  mov     eax, [rbx]
0x1400180e3  mov     [r11+4], eax
0x1400180e7  mov     r8d, [rbx+8]
0x1400180eb  mov     [r11+1Ch], r8d
0x1400180ef  mov     al, [rbx+1Ch]
0x1400180f2  neg     al
0x1400180f4  sbb     ecx, ecx
0x1400180f6  imul    r8d, edx
0x1400180fa  and     ecx, 11h
0x1400180fd  add     ecx, 9Ch
0x140018103  mov     [r11], ecx
0x140018106  mov     rcx, r11; this
0x140018109  imul    r8d, r9d
0x14001810d  add     r8d, r8d
0x140018110  mov     [r11+40h], r8d
0x140018114  call    ?CalculateSbcFrameLength@SbcControl@SBC@@QEBAHXZ; SBC::SbcControl::CalculateSbcFrameLength(void)
0x140018119  lea     rcx, [r11+0CE8h]; void *
0x140018120  mov     [r11+44h], eax
0x140018124  xor     edx, edx; Val
0x140018126  mov     r8d, 140h; Size
0x14001812c  call    memset
0x140018131  mov     rbx, [rsp+28h+arg_0]
0x140018136  mov     eax, edi
0x140018138  add     rsp, 20h
0x14001813c  pop     rdi
0x14001813d  retn
```
