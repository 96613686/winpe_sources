# InstallDeviceEndpoints(_MMPNPINFO *,ushort const *,unsigned __int64,ulong)

- ea: `0x18000db00`
- end: `0x18000dc3e`
- name: `?InstallDeviceEndpoints@@YAPEAU_MMDEVICEINTERFACEINFO@@PEAU_MMPNPINFO@@PEBG_KK@Z`
- size: `318`
- prototype: `struct _MMDEVICEINTERFACEINFO *(struct _MMPNPINFO *, const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000d000`

## callees

- `0x18000db00`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000db4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000db4a`

## pseudocode

```c
struct _MMDEVICEINTERFACEINFO *__fastcall InstallDeviceEndpoints(
        struct _MMPNPINFO *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4)
{
  int v4; // ebp
  unsigned __int64 v5; // r14
  __int64 v10; // rsi
  unsigned __int64 v11; // rdi
  struct _MMDEVICEINTERFACEINFO *result; // rax
  __int64 v13; // rax
  bool v14; // zf
  unsigned __int64 v15; // r9
  _WORD *v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // rcx
  _WORD *v19; // rax

  v4 = *((_DWORD *)a1 + 2);
  v5 = ((unsigned __int64)a1 + 19) & 0xFFFFFFFFFFFFFFF8uLL;
  v10 = -1;
  if ( v4 )
  {
    while ( 1 )
    {
      v11 = v5 + 12;
      if ( !lstrcmpiW((LPCWSTR)(v5 + 12), a2) )
        break;
      v13 = -1;
      do
        v14 = *(_WORD *)(v11 + 2 * v13++ + 2) == 0;
      while ( !v14 );
      v5 = (v11 + 2 * v13 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !--v4 )
        goto LABEL_9;
    }
  }
  else
  {
    do
LABEL_9:
      v14 = a2[++v10] == 0;
    while ( !v14 );
    v15 = ((v5 + 2 * v10 + 21) & 0xFFFFFFFFFFFFFFF8uLL) - (_QWORD)a1;
    if ( v15 >= 0x40000 )
      return 0;
    v16 = (_WORD *)(v5 + 12);
    *(_QWORD *)v5 = 0;
    *(_DWORD *)(v5 + 8) = 0;
    v17 = (((v5 + 2 * v10 + 21) & 0xFFFFFFFFFFFFFFF8uLL) - (v5 + 12)) >> 1;
    if ( v17 )
    {
      if ( v17 > 0x7FFFFFFF )
      {
        *v16 = 0;
      }
      else
      {
        v18 = 2147483646;
        do
        {
          if ( !v18 )
            break;
          if ( !*a2 )
            break;
          *v16++ = *a2++;
          --v18;
          --v17;
        }
        while ( v17 );
        v19 = v16 - 1;
        if ( v17 )
          v19 = v16;
        *v19 = 0;
      }
    }
    ++*((_DWORD *)a1 + 2);
    *(_DWORD *)a1 = v15;
  }
  result = (struct _MMDEVICEINTERFACEINFO *)v5;
  if ( v5 )
  {
    *(_DWORD *)(v5 + 8) &= ~1u;
    *(_DWORD *)(v5 + 8) |= a4;
    *(_QWORD *)v5 = a3;
  }
  return result;
}

```

## disassembly

```asm
0x18000db00  push    rbx
0x18000db02  push    rbp
0x18000db03  push    rsi
0x18000db04  push    rdi
0x18000db05  push    r12
0x18000db07  push    r13
0x18000db09  push    r14
0x18000db0b  push    r15
0x18000db0d  sub     rsp, 28h
0x18000db11  mov     ebp, [rcx+8]
0x18000db14  lea     r14, [rcx+13h]
0x18000db18  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000db1c  mov     r12d, r9d
0x18000db1f  mov     r13, r8
0x18000db22  mov     rbx, rdx
0x18000db25  mov     r15, rcx
0x18000db28  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000db2f  test    ebp, ebp
0x18000db31  jz      short loc_18000DB94
0x18000db33  nop     dword ptr [rax+00h]
0x18000db37  nop     word ptr [rax+rax+00000000h]
0x18000db40  lea     rdi, [r14+0Ch]
0x18000db44  mov     rdx, rbx; lpString2
0x18000db47  mov     rcx, rdi; lpString1
0x18000db4a  call    cs:__imp_lstrcmpiW
0x18000db50  test    eax, eax
0x18000db52  jnz     short loc_18000DB71
0x18000db54  mov     rax, r14
0x18000db57  test    r14, r14
0x18000db5a  jnz     loc_18000DC2D
0x18000db60  add     rsp, 28h
0x18000db64  pop     r15
0x18000db66  pop     r14
0x18000db68  pop     r13
0x18000db6a  pop     r12
0x18000db6c  pop     rdi
0x18000db6d  pop     rsi
0x18000db6e  pop     rbp
0x18000db6f  pop     rbx
0x18000db70  retn
0x18000db71  mov     rax, rsi
0x18000db74  cmp     word ptr [rdi+rax*2+2], 0
0x18000db7a  lea     rax, [rax+1]
0x18000db7e  jnz     short loc_18000DB74
0x18000db80  lea     r14, ds:9[rax*2]
0x18000db88  add     r14, rdi
0x18000db8b  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000db8f  add     ebp, 0FFFFFFFFh
0x18000db92  jnz     short loc_18000DB40
0x18000db94  cmp     word ptr [rbx+rsi*2+2], 0
0x18000db9a  lea     rsi, [rsi+1]
0x18000db9e  jnz     short loc_18000DB94
0x18000dba0  lea     rdx, ds:15h[rsi*2]
0x18000dba8  xor     r10d, r10d
0x18000dbab  add     rdx, r14
0x18000dbae  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000dbb2  mov     r9, rdx
0x18000dbb5  sub     r9, r15
0x18000dbb8  cmp     r9, 40000h
0x18000dbbf  jnb     short loc_18000DC1F
0x18000dbc1  lea     r8, [r14+0Ch]
0x18000dbc5  mov     [r14], r10
0x18000dbc8  sub     rdx, r8
0x18000dbcb  mov     [r14+8], r10d
0x18000dbcf  shr     rdx, 1
0x18000dbd2  jz      short loc_18000DC13
0x18000dbd4  cmp     rdx, 7FFFFFFFh
0x18000dbdb  ja      short loc_18000DC27
0x18000dbdd  mov     ecx, 7FFFFFFEh
0x18000dbe2  test    rcx, rcx
0x18000dbe5  jz      short loc_18000DC04
0x18000dbe7  movzx   eax, word ptr [rbx]
0x18000dbea  test    ax, ax
0x18000dbed  jz      short loc_18000DC04
0x18000dbef  mov     [r8], ax
0x18000dbf3  add     rbx, 2
0x18000dbf7  add     r8, 2
0x18000dbfb  dec     rcx
0x18000dbfe  sub     rdx, 1
0x18000dc02  jnz     short loc_18000DBE2
0x18000dc04  test    rdx, rdx
0x18000dc07  lea     rax, [r8-2]
0x18000dc0b  cmovnz  rax, r8
0x18000dc0f  mov     [rax], r10w
0x18000dc13  inc     dword ptr [r15+8]
0x18000dc17  mov     [r15], r9d
0x18000dc1a  jmp     loc_18000DB54
0x18000dc1f  mov     rax, r10
0x18000dc22  jmp     loc_18000DB60
0x18000dc27  mov     [r8], r10w
0x18000dc2b  jmp     short loc_18000DC13
0x18000dc2d  and     dword ptr [r14+8], 0FFFFFFFEh
0x18000dc32  or      [r14+8], r12d
0x18000dc36  mov     [r14], r13
0x18000dc39  jmp     loc_18000DB60
```
