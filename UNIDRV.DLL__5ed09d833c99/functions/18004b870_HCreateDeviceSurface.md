# HCreateDeviceSurface

- ea: `0x18004b870`
- end: `0x18004b947`
- name: `HCreateDeviceSurface`
- size: `215`
- prototype: `HSURF __fastcall(DHSURF, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a8f0`

## callees

- `0x18004b870`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18004b928`
- `KERNEL32!SetLastError` at `0x18004b928`
- `GDI32!EngCreateDeviceSurface` at `0x18004b8cc`
- `GDI32!EngCreateDeviceSurface` at `0x18004b8cc`

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
0x18004b870  mov     [rsp+arg_8], rbx
0x18004b875  mov     [rsp+arg_10], rsi
0x18004b87a  push    rdi
0x18004b87b  sub     rsp, 20h
0x18004b87f  mov     qword ptr [rsp+28h+sizl.cx], 0
0x18004b888  mov     rbx, rcx
0x18004b88b  test    rcx, rcx
0x18004b88e  jz      loc_18004B923
0x18004b894  cmp     rcx, [rcx+40h]
0x18004b898  jnz     loc_18004B923
0x18004b89e  cmp     rcx, [rcx+1148h]
0x18004b8a5  jnz     short loc_18004B923
0x18004b8a7  cmp     dword ptr [rcx+48h], 72706476h
0x18004b8ae  jnz     short loc_18004B923
0x18004b8b0  mov     edi, [rcx+0FECh]
0x18004b8b6  mov     r8d, edx; iFormatCompat
0x18004b8b9  mov     esi, [rcx+0FF0h]
0x18004b8bf  mov     [rsp+28h+sizl.cx], edi
0x18004b8c3  mov     [rsp+28h+sizl.cy], esi
0x18004b8c7  mov     rdx, qword ptr [rsp+28h+sizl.cx]; sizl
0x18004b8cc  call    cs:__imp_EngCreateDeviceSurface
0x18004b8d3  nop     dword ptr [rax+rax+00h]
0x18004b8d8  mov     rcx, rax
0x18004b8db  test    rax, rax
0x18004b8de  jnz     short loc_18004B8E5
0x18004b8e0  lea     ecx, [rax+77h]
0x18004b8e3  jmp     short loc_18004B928
0x18004b8e5  mov     eax, [rbx+0FECh]
0x18004b8eb  mov     [rbx+7C4h], eax
0x18004b8f1  mov     eax, [rbx+0FF0h]
0x18004b8f7  mov     [rbx+7C8h], eax
0x18004b8fd  mov     rax, rcx
0x18004b900  mov     qword ptr [rbx+7BCh], 0
0x18004b90b  mov     dword ptr [rbx+7A8h], 0
0x18004b915  mov     [rbx+7B4h], edi
0x18004b91b  mov     [rbx+7B8h], esi
0x18004b921  jmp     short loc_18004B936
0x18004b923  mov     ecx, 57h ; 'W'; dwErrCode
0x18004b928  call    cs:__imp_SetLastError
0x18004b92f  nop     dword ptr [rax+rax+00h]
0x18004b934  xor     eax, eax
0x18004b936  mov     rbx, [rsp+28h+arg_8]
0x18004b93b  mov     rsi, [rsp+28h+arg_10]
0x18004b940  add     rsp, 20h
0x18004b944  pop     rdi
0x18004b945  retn
```
