# HCreateDeviceSurface

- ea: `0x18004a294`
- end: `0x18004a35a`
- name: `HCreateDeviceSurface`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800493a0`

## callees

- `0x18004a294`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18004a342`
- `KERNEL32!SetLastError` at `0x18004a342`
- `GDI32!EngCreateDeviceSurface` at `0x18004a2ec`
- `GDI32!EngCreateDeviceSurface` at `0x18004a2ec`

## pseudocode

```c
HSURF __fastcall HCreateDeviceSurface(DHSURF a1, ULONG a2)
{
  int v3; // edi
  int v4; // esi
  HSURF result; // rax
  DWORD v6; // ecx

  if ( a1 && a1 == *((DHSURF *)a1 + 8) && a1 == *((DHSURF *)a1 + 553) && *((_DWORD *)a1 + 18) == 1919968374 )
  {
    v3 = *((_DWORD *)a1 + 1019);
    v4 = *((_DWORD *)a1 + 1020);
    result = EngCreateDeviceSurface(a1, *(SIZEL *)(a1 + 1019), a2);
    if ( result )
    {
      a1[497] = a1[1019];
      a1[498] = a1[1020];
      *(_QWORD *)(a1 + 495) = 0;
      *((_DWORD *)a1 + 490) = 0;
      *((_DWORD *)a1 + 493) = v3;
      *((_DWORD *)a1 + 494) = v4;
      return result;
    }
    v6 = 119;
  }
  else
  {
    v6 = 87;
  }
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18004a294  mov     [rsp+arg_8], rbx
0x18004a299  mov     [rsp+arg_10], rsi
0x18004a29e  push    rdi
0x18004a29f  sub     rsp, 20h
0x18004a2a3  mov     qword ptr [rsp+28h+sizl.cx], 0
0x18004a2ac  mov     rbx, rcx
0x18004a2af  test    rcx, rcx
0x18004a2b2  jz      loc_18004A33D
0x18004a2b8  cmp     rcx, [rcx+40h]
0x18004a2bc  jnz     short loc_18004A33D
0x18004a2be  cmp     rcx, [rcx+1148h]
0x18004a2c5  jnz     short loc_18004A33D
0x18004a2c7  cmp     dword ptr [rcx+48h], 72706476h
0x18004a2ce  jnz     short loc_18004A33D
0x18004a2d0  mov     edi, [rcx+0FECh]
0x18004a2d6  mov     r8d, edx; iFormatCompat
0x18004a2d9  mov     esi, [rcx+0FF0h]
0x18004a2df  mov     [rsp+28h+sizl.cx], edi
0x18004a2e3  mov     [rsp+28h+sizl.cy], esi
0x18004a2e7  mov     rdx, qword ptr [rsp+28h+sizl.cx]; sizl
0x18004a2ec  call    cs:__imp_EngCreateDeviceSurface
0x18004a2f2  mov     rcx, rax
0x18004a2f5  test    rax, rax
0x18004a2f8  jnz     short loc_18004A2FF
0x18004a2fa  lea     ecx, [rax+77h]
0x18004a2fd  jmp     short loc_18004A342
0x18004a2ff  mov     eax, [rbx+0FECh]
0x18004a305  mov     [rbx+7C4h], eax
0x18004a30b  mov     eax, [rbx+0FF0h]
0x18004a311  mov     [rbx+7C8h], eax
0x18004a317  mov     rax, rcx
0x18004a31a  mov     qword ptr [rbx+7BCh], 0
0x18004a325  mov     dword ptr [rbx+7A8h], 0
0x18004a32f  mov     [rbx+7B4h], edi
0x18004a335  mov     [rbx+7B8h], esi
0x18004a33b  jmp     short loc_18004A34A
0x18004a33d  mov     ecx, 57h ; 'W'; dwErrCode
0x18004a342  call    cs:__imp_SetLastError
0x18004a348  xor     eax, eax
0x18004a34a  mov     rbx, [rsp+28h+arg_8]
0x18004a34f  mov     rsi, [rsp+28h+arg_10]
0x18004a354  add     rsp, 20h
0x18004a358  pop     rdi
0x18004a359  retn
```
