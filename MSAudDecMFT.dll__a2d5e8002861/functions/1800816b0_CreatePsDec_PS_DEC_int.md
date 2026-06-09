# CreatePsDec(PS_DEC * *,int)

- ea: `0x1800816b0`
- end: `0x1800817bc`
- name: `?CreatePsDec@@YAHPEAPEAUPS_DEC@@H@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct PS_DEC **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b418`

## callees

- `0x18004775c`
- `0x18004dd14`
- `0x1800816b0`
- `0x1800817c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800816d4`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800816d4`

## pseudocode

```c
__int64 __fastcall CreatePsDec(struct PS_DEC **a1, int a2)
{
  struct PS_DEC *v2; // rbx
  int v3; // edi
  __int64 result; // rax
  int v6; // edi
  struct PS_DEC *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  v3 = a2;
  if ( *a1 )
  {
    v7 = *a1;
  }
  else
  {
    v7 = (struct PS_DEC *)calloc(1u, 0x3A00u);
    v2 = v7;
    if ( !v7 )
      goto LABEL_3;
  }
  *((_QWORD *)v2 + 179) = 312;
  *((_QWORD *)v2 + 177) = (char *)v2 + 824;
  *((_QWORD *)v2 + 178) = 0;
  v6 = v3 - 960;
  if ( v6 )
  {
    if ( v6 != 64 )
    {
      *(_BYTE *)v2 = -1;
      goto LABEL_3;
    }
    *(_BYTE *)v2 = 32;
  }
  else
  {
    *(_BYTE *)v2 = 30;
  }
  *(_WORD *)((char *)v2 + 1) = -192;
  *((_BYTE *)v2 + 12) = 0;
  LOBYTE(a2) = 0;
  *(_QWORD *)((char *)v2 + 4) = 0;
  *((_DWORD *)v2 + 370) = 0;
  *((_QWORD *)v2 + 186) = (char *)v2 + 4904;
  *((_QWORD *)v2 + 188) = 0;
  *((_DWORD *)v2 + 374) = 0;
  memset_0((char *)v2 + 16, a2, 0x2DEu);
  result = ResetPsDec(v2);
  if ( !(_DWORD)result )
  {
    *a1 = v2;
    return result;
  }
LABEL_3:
  if ( v2 )
    DeletePsDec(&v7);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800816b0  mov     [rsp+arg_8], rbx
0x1800816b5  mov     [rsp+arg_10], rsi
0x1800816ba  push    rdi
0x1800816bb  sub     rsp, 20h
0x1800816bf  mov     rbx, [rcx]
0x1800816c2  mov     edi, edx
0x1800816c4  mov     rsi, rcx
0x1800816c7  test    rbx, rbx
0x1800816ca  jnz     short loc_180081710
0x1800816cc  mov     edx, 3A00h; Size
0x1800816d1  lea     ecx, [rbx+1]; Count
0x1800816d4  call    cs:__imp_calloc
0x1800816db  nop     dword ptr [rax+rax+00h]
0x1800816e0  mov     [rsp+28h+arg_0], rax
0x1800816e5  mov     rbx, rax
0x1800816e8  test    rax, rax
0x1800816eb  jnz     short loc_180081715
0x1800816ed  test    rbx, rbx
0x1800816f0  jz      short loc_1800816FC
0x1800816f2  lea     rcx, [rsp+28h+arg_0]; struct PS_DEC **
0x1800816f7  call    ?DeletePsDec@@YAHPEAPEAUPS_DEC@@@Z; DeletePsDec(PS_DEC * *)
0x1800816fc  or      eax, 0FFFFFFFFh
0x1800816ff  mov     rbx, [rsp+28h+arg_8]
0x180081704  mov     rsi, [rsp+28h+arg_10]
0x180081709  add     rsp, 20h
0x18008170d  pop     rdi
0x18008170e  retn
0x180081710  mov     [rsp+28h+arg_0], rbx
0x180081715  mov     qword ptr [rbx+598h], 138h
0x180081720  lea     rax, [rbx+338h]
0x180081727  mov     [rbx+588h], rax
0x18008172e  mov     rcx, rbx
0x180081731  mov     qword ptr [rbx+590h], 0
0x18008173c  sub     edi, 3C0h
0x180081742  jz      short loc_180081753
0x180081744  cmp     edi, 40h ; '@'
0x180081747  jz      short loc_18008174E
0x180081749  mov     byte ptr [rbx], 0FFh
0x18008174c  jmp     short loc_1800816ED
0x18008174e  mov     byte ptr [rbx], 20h ; ' '
0x180081751  jmp     short loc_180081756
0x180081753  mov     byte ptr [rbx], 1Eh
0x180081756  mov     word ptr [rcx+1], 0FF40h
0x18008175c  xor     eax, eax
0x18008175e  mov     byte ptr [rcx+0Ch], 0
0x180081762  xor     dl, dl; Val
0x180081764  mov     [rcx+4], rax
0x180081768  mov     r8d, 2DEh; Size
0x18008176e  lea     rax, [rbx+1328h]
0x180081775  mov     dword ptr [rbx+5C8h], 0
0x18008177f  add     rcx, 10h; void *
0x180081783  mov     [rbx+5D0h], rax
0x18008178a  mov     qword ptr [rbx+5E0h], 0
0x180081795  mov     dword ptr [rbx+5D8h], 0
0x18008179f  call    memset_0
0x1800817a4  mov     rcx, rbx
0x1800817a7  call    ?ResetPsDec@@YA?AW4SBR_ERROR@@PEAUPS_DEC@@@Z; ResetPsDec(PS_DEC *)
0x1800817ac  test    eax, eax
0x1800817ae  jnz     loc_1800816ED
0x1800817b4  mov     [rsi], rbx
0x1800817b7  jmp     loc_1800816FF
```
