# AutoThreadPriority::GetPlatformPriorityFromPriority(AutoThreadPriority::PriorityType)

- ea: `0x1400246a0`
- end: `0x140024726`
- name: `?GetPlatformPriorityFromPriority@AutoThreadPriority@@SA?AUPlatformPriority@1@W4PriorityType@1@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400246a0`
- `0x140024cf8`

## callees

- `0x1400246a0`

## pseudocode

```c
__int64 __fastcall AutoThreadPriority::GetPlatformPriorityFromPriority(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx

  v3 = a2 - 1;
  if ( !v3 )
  {
    *(_BYTE *)(a1 + 12) = 0;
    goto LABEL_10;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    *(_DWORD *)a1 = -1;
    *(_DWORD *)(a1 + 8) = 2;
    *(_BYTE *)(a1 + 12) = 1;
LABEL_11:
    *(_DWORD *)(a1 + 4) = 2;
    goto LABEL_12;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    *(_DWORD *)a1 = -2;
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)(a1 + 8) = 2;
    *(_BYTE *)(a1 + 12) = 1;
LABEL_12:
    *(_WORD *)(a1 + 13) = 0;
    *(_BYTE *)(a1 + 15) = 0;
    return a1;
  }
  if ( v5 == 1 )
  {
    *(_BYTE *)(a1 + 12) = 1;
LABEL_10:
    *(_DWORD *)a1 = 0;
    *(_DWORD *)(a1 + 8) = 5;
    goto LABEL_11;
  }
  AutoThreadPriority::GetPlatformPriorityFromPriority(a1, 1);
  return a1;
}

```

## disassembly

```asm
0x1400246a0  push    rbx
0x1400246a2  sub     rsp, 20h
0x1400246a6  mov     rbx, rcx
0x1400246a9  sub     edx, 1
0x1400246ac  jz      short loc_1400246FC
0x1400246ae  sub     edx, 1
0x1400246b1  jz      short loc_1400246E9
0x1400246b3  sub     edx, 1
0x1400246b6  jz      short loc_1400246CF
0x1400246b8  cmp     edx, 1
0x1400246bb  jz      short loc_1400246C9
0x1400246bd  mov     edx, 1
0x1400246c2  call    ?GetPlatformPriorityFromPriority@AutoThreadPriority@@SA?AUPlatformPriority@1@W4PriorityType@1@@Z; AutoThreadPriority::GetPlatformPriorityFromPriority(AutoThreadPriority::PriorityType)
0x1400246c7  jmp     short loc_14002471D
0x1400246c9  mov     byte ptr [rcx+0Ch], 1
0x1400246cd  jmp     short loc_140024700
0x1400246cf  mov     dword ptr [rcx], 0FFFFFFFEh
0x1400246d5  mov     dword ptr [rcx+4], 0
0x1400246dc  mov     dword ptr [rcx+8], 2
0x1400246e3  mov     byte ptr [rcx+0Ch], 1
0x1400246e7  jmp     short loc_140024714
0x1400246e9  mov     dword ptr [rcx], 0FFFFFFFFh
0x1400246ef  mov     dword ptr [rcx+8], 2
0x1400246f6  mov     byte ptr [rcx+0Ch], 1
0x1400246fa  jmp     short loc_14002470D
0x1400246fc  mov     byte ptr [rcx+0Ch], 0
0x140024700  mov     dword ptr [rcx], 0
0x140024706  mov     dword ptr [rcx+8], 5
0x14002470d  mov     dword ptr [rcx+4], 2
0x140024714  xor     eax, eax
0x140024716  mov     [rcx+0Dh], ax
0x14002471a  mov     [rcx+0Fh], al
0x14002471d  mov     rax, rbx
0x140024720  add     rsp, 20h
0x140024724  pop     rbx
0x140024725  retn
```
