# DloadProtectSection

- ea: `0x180009900`
- end: `0x1800099e7`
- name: `DloadProtectSection`
- size: `231`
- prototype: `__int64 __fastcall(DWORD flNewProtect, PDWORD lpflOldProtect)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800097d0`
- `0x1800099f0`

## callees

- `0x180009834`
- `0x180009900`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800099c0`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800099c0`

## pseudocode

```c
void __fastcall DloadProtectSection(DWORD flNewProtect, PDWORD lpflOldProtect)
{
  __int64 v4; // r9
  unsigned int v5; // r10d
  int *v6; // rcx
  unsigned int i; // r9d
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  char *v10; // rdi
  bool v11; // sf
  SIZE_T v12; // rbx

  if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
  {
    v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
    if ( (_DWORD)v4 )
    {
      v5 = *(_DWORD *)((char *)&word_18000000C + v4);
      v6 = (int *)((char *)&_ImageBase
                 + (int)off_18000003C
                 + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                 + 24);
      for ( i = 0; i < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C); ++i )
      {
        v8 = (unsigned int)v6[3];
        if ( v5 >= (unsigned int)v8 )
        {
          v9 = (unsigned int)v6[2];
          if ( v5 < (int)v9 + (int)v8 )
          {
            v10 = (char *)&_ImageBase + v8;
            if ( !(__int16 *)((char *)&_ImageBase + v8) )
              break;
            if ( DloadSectionCommitPermanent )
            {
              v12 = (unsigned int)v6[2];
            }
            else
            {
              v11 = v6[9] < 0;
              DloadSectionCommitPermanent = 1;
              if ( !v11 )
                __fastfail(0x19u);
              v12 = v9;
              DloadMakePermanentImageCommit((unsigned __int64)v10, v9);
            }
            if ( !VirtualProtect(v10, v12, flNewProtect, lpflOldProtect) )
              __fastfail(0x19u);
            return;
          }
        }
        v6 += 10;
      }
    }
  }
  *lpflOldProtect = 4;
}

```

## disassembly

```asm
0x180009900  push    rbx
0x180009902  push    rbp
0x180009903  push    rsi
0x180009904  push    rdi
0x180009905  sub     rsp, 28h
0x180009909  movsxd  r8, cs:off_18000003C
0x180009910  lea     rbx, __ImageBase
0x180009917  add     r8, rbx
0x18000991a  mov     rsi, rdx
0x18000991d  mov     ebp, ecx
0x18000991f  cmp     dword ptr [r8+84h], 0Dh
0x180009927  jbe     loc_1800099D7
0x18000992d  mov     r9d, [r8+0F0h]
0x180009934  test    r9d, r9d
0x180009937  jz      loc_1800099D7
0x18000993d  movzx   ecx, word ptr [r8+14h]
0x180009942  mov     r10d, [r9+rbx+0Ch]
0x180009947  add     rcx, 18h
0x18000994b  movzx   r11d, word ptr [r8+6]
0x180009950  add     rcx, r8
0x180009953  xor     r9d, r9d
0x180009956  cmp     r9d, r11d
0x180009959  jnb     short loc_1800099D7
0x18000995b  mov     edx, [rcx+0Ch]
0x18000995e  cmp     r10d, edx
0x180009961  jb      short loc_180009970
0x180009963  mov     r8d, [rcx+8]
0x180009967  lea     eax, [r8+rdx]
0x18000996b  cmp     r10d, eax
0x18000996e  jb      short loc_180009979
0x180009970  inc     r9d
0x180009973  add     rcx, 28h ; '('
0x180009977  jmp     short loc_180009956
0x180009979  mov     rdi, rdx
0x18000997c  add     rdi, rbx
0x18000997f  jz      short loc_1800099D7
0x180009981  cmp     cs:DloadSectionCommitPermanent, 0
0x180009988  jnz     short loc_1800099B1
0x18000998a  cmp     dword ptr [rcx+24h], 0
0x18000998e  mov     cs:DloadSectionCommitPermanent, 1
0x180009998  jl      short loc_1800099A1
0x18000999a  mov     ecx, 19h
0x18000999f  int     29h; Win8: RtlFailFast(ecx)
0x1800099a1  mov     rdx, r8
0x1800099a4  mov     rcx, rdi
0x1800099a7  mov     rbx, r8
0x1800099aa  call    DloadMakePermanentImageCommit
0x1800099af  jmp     short loc_1800099B4
0x1800099b1  mov     rbx, r8
0x1800099b4  mov     r9, rsi; lpflOldProtect
0x1800099b7  mov     r8d, ebp; flNewProtect
0x1800099ba  mov     rdx, rbx; dwSize
0x1800099bd  mov     rcx, rdi; lpAddress
0x1800099c0  call    cs:__imp_VirtualProtect
0x1800099c7  nop     dword ptr [rax+rax+00h]
0x1800099cc  test    eax, eax
0x1800099ce  jnz     short loc_1800099DD
0x1800099d0  lea     ecx, [rax+19h]
0x1800099d3  int     29h; Win8: RtlFailFast(ecx)
0x1800099d5  jmp     short loc_1800099DD
0x1800099d7  mov     dword ptr [rsi], 4
0x1800099dd  add     rsp, 28h
0x1800099e1  pop     rdi
0x1800099e2  pop     rsi
0x1800099e3  pop     rbp
0x1800099e4  pop     rbx
0x1800099e5  retn
```
