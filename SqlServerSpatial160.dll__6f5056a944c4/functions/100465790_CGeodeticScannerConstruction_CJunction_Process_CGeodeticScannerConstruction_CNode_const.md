# CGeodeticScannerConstruction::CJunction::Process(CGeodeticScannerConstruction::CNode const &)

- ea: `0x100465790`
- end: `0x100465867`
- name: `?Process@CJunction@CGeodeticScannerConstruction@@QEAAXAEBVCNode@2@@Z`
- size: `215`
- prototype: `void __fastcall(CGeodeticScannerConstruction::CJunction *__hidden this, const struct CGeodeticScannerConstruction::CNode *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x100462e10`

## callees

- `0x100465790`

## pseudocode

```c
void __fastcall CGeodeticScannerConstruction::CJunction::Process(
        CGeodeticScannerConstruction::CJunction *this,
        const struct CGeodeticScannerConstruction::CNode *a2)
{
  __int64 v4; // rcx
  char v5; // al
  char v6; // dl
  __int64 v7; // rcx
  char v8; // al
  char v9; // dl

  v4 = *((_QWORD *)a2 + 3);
  if ( v4 )
  {
    v5 = *(_BYTE *)(v4 + 85);
    if ( (v5 & 1) == 0 )
    {
      if ( (v5 & 2) != 0 )
      {
        v6 = *(_BYTE *)(v4 + 84);
        if ( (v5 & 4) != 0 )
        {
          if ( v6 )
            *((_QWORD *)this + 4) = v4;
          else
            *((_QWORD *)this + 2) = v4;
        }
        else if ( v6 )
        {
          *((_QWORD *)this + 5) = v4;
        }
        else
        {
          *((_QWORD *)this + 3) = v4;
        }
      }
      else
      {
        *((_QWORD *)this + *((unsigned int *)this + 40) + 10) = v4;
        *((_BYTE *)this + (unsigned int)(*((_DWORD *)this + 40))++ + 168) = (*(_BYTE *)(v4 + 85) & 0x40) == 0;
      }
    }
  }
  v7 = *((_QWORD *)a2 + 4);
  if ( v7 )
  {
    v8 = *(_BYTE *)(v7 + 85);
    if ( (v8 & 1) == 0 )
    {
      if ( (v8 & 2) != 0 )
      {
        v9 = *(_BYTE *)(v7 + 84);
        if ( (v8 & 4) != 0 )
        {
          if ( v9 )
            *((_QWORD *)this + 6) = v7;
          else
            *((_QWORD *)this + 8) = v7;
        }
        else if ( v9 )
        {
          *((_QWORD *)this + 9) = v7;
        }
        else
        {
          *((_QWORD *)this + 7) = v7;
        }
      }
      else
      {
        *((_QWORD *)this + *((unsigned int *)this + 40) + 10) = v7;
        *((_BYTE *)this + (unsigned int)(*((_DWORD *)this + 40))++ + 168) = (*(_BYTE *)(v7 + 85) & 0x40) != 0;
      }
    }
  }
}

```

## disassembly

```asm
0x100465790  mov     r8, rcx
0x100465793  mov     r9, rdx
0x100465796  mov     rcx, [rdx+18h]
0x10046579a  test    rcx, rcx
0x10046579d  jz      short loc_100465801
0x10046579f  movzx   eax, byte ptr [rcx+55h]
0x1004657a3  test    al, 1
0x1004657a5  jnz     short loc_100465801
0x1004657a7  test    al, 2
0x1004657a9  jz      short loc_1004657D3
0x1004657ab  movzx   edx, byte ptr [rcx+54h]
0x1004657af  test    al, 4
0x1004657b1  jz      short loc_1004657C3
0x1004657b3  test    dl, dl
0x1004657b5  jnz     short loc_1004657BD
0x1004657b7  mov     [r8+10h], rcx
0x1004657bb  jmp     short loc_100465801
0x1004657bd  mov     [r8+20h], rcx
0x1004657c1  jmp     short loc_100465801
0x1004657c3  test    dl, dl
0x1004657c5  jnz     short loc_1004657CD
0x1004657c7  mov     [r8+18h], rcx
0x1004657cb  jmp     short loc_100465801
0x1004657cd  mov     [r8+28h], rcx
0x1004657d1  jmp     short loc_100465801
0x1004657d3  mov     eax, [r8+0A0h]
0x1004657da  mov     [r8+rax*8+50h], rcx
0x1004657df  movzx   ecx, byte ptr [rcx+55h]
0x1004657e3  mov     eax, [r8+0A0h]
0x1004657ea  shr     cl, 6
0x1004657ed  not     cl
0x1004657ef  and     cl, 1
0x1004657f2  mov     [rax+r8+0A8h], cl
0x1004657fa  inc     dword ptr [r8+0A0h]
0x100465801  mov     rcx, [r9+20h]
0x100465805  test    rcx, rcx
0x100465808  jz      short locret_100465866
0x10046580a  movzx   eax, byte ptr [rcx+55h]
0x10046580e  test    al, 1
0x100465810  jnz     short locret_100465866
0x100465812  test    al, 2
0x100465814  jz      short loc_10046583A
0x100465816  movzx   edx, byte ptr [rcx+54h]
0x10046581a  test    al, 4
0x10046581c  jz      short loc_10046582C
0x10046581e  test    dl, dl
0x100465820  jnz     short loc_100465827
0x100465822  mov     [r8+40h], rcx
0x100465826  retn
0x100465827  mov     [r8+30h], rcx
0x10046582b  retn
0x10046582c  test    dl, dl
0x10046582e  jnz     short loc_100465835
0x100465830  mov     [r8+38h], rcx
0x100465834  retn
0x100465835  mov     [r8+48h], rcx
0x100465839  retn
0x10046583a  mov     eax, [r8+0A0h]
0x100465841  mov     [r8+rax*8+50h], rcx
0x100465846  movzx   ecx, byte ptr [rcx+55h]
0x10046584a  mov     eax, [r8+0A0h]
0x100465851  shr     cl, 6
0x100465854  and     cl, 1
0x100465857  mov     [rax+r8+0A8h], cl
0x10046585f  inc     dword ptr [r8+0A0h]
0x100465866  retn
```
