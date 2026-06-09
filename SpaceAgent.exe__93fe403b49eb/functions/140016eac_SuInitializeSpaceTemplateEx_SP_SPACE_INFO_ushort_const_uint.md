# SuInitializeSpaceTemplateEx(_SP_SPACE_INFO *,ushort const *,uint)

- ea: `0x140016eac`
- end: `0x140016f42`
- name: `?SuInitializeSpaceTemplateEx@@YAHPEAU_SP_SPACE_INFO@@PEBGI@Z`
- size: `150`
- prototype: `__int64 __fastcall(struct _SP_SPACE_INFO *, size_t *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018a8c`

## callees

- `0x140008190`
- `0x140016eac`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140016eff`
- `KERNEL32!SetLastError` at `0x140016eff`

## pseudocode

```c
__int64 __fastcall SuInitializeSpaceTemplateEx(struct _SP_SPACE_INFO *a1, size_t *a2, int a3)
{
  unsigned int v4; // ebx
  _DWORD *v5; // r11
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx

  v4 = 1;
  StringCchCopyW((unsigned __int16 *)a1 + 20, 0x100u, a2);
  v6 = v5[687];
  v5[674] = 1;
  v5[688] = a3;
  v5[690] = 1;
  v7 = v6 - 1;
  if ( !v7 )
  {
    v5[691] = 1;
    goto LABEL_8;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v5[691] = 1;
    v5[689] = a3 + 1;
    return v4;
  }
  if ( v8 == 1 )
  {
    v5[691] = 3;
LABEL_8:
    v5[689] = 1;
    return v4;
  }
  v4 = 0;
  SetLastError(0x57u);
  return v4;
}

```

## disassembly

```asm
0x140016eac  mov     [rsp+arg_0], rbx
0x140016eb1  push    rdi
0x140016eb2  sub     rsp, 20h
0x140016eb6  mov     edi, r8d
0x140016eb9  mov     r11, rcx
0x140016ebc  mov     r8, rdx; unsigned __int16 *
0x140016ebf  add     rcx, 28h ; '('; unsigned __int16 *
0x140016ec3  mov     edx, 100h; unsigned __int64
0x140016ec8  mov     ebx, 1
0x140016ecd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140016ed2  mov     ecx, [r11+0ABCh]
0x140016ed9  mov     [r11+0A88h], ebx
0x140016ee0  mov     [r11+0AC0h], edi
0x140016ee7  mov     [r11+0AC8h], ebx
0x140016eee  sub     ecx, ebx
0x140016ef0  jz      short loc_140016F27
0x140016ef2  sub     ecx, ebx
0x140016ef4  jz      short loc_140016F14
0x140016ef6  cmp     ecx, ebx
0x140016ef8  jz      short loc_140016F07
0x140016efa  xor     ebx, ebx
0x140016efc  lea     ecx, [rbx+57h]; dwErrCode
0x140016eff  call    cs:__imp_SetLastError
0x140016f05  jmp     short loc_140016F35
0x140016f07  mov     dword ptr [r11+0ACCh], 3
0x140016f12  jmp     short loc_140016F2E
0x140016f14  lea     eax, [rdi+1]
0x140016f17  mov     [r11+0ACCh], ebx
0x140016f1e  mov     [r11+0AC4h], eax
0x140016f25  jmp     short loc_140016F35
0x140016f27  mov     [r11+0ACCh], ebx
0x140016f2e  mov     [r11+0AC4h], ebx
0x140016f35  mov     eax, ebx
0x140016f37  mov     rbx, [rsp+28h+arg_0]
0x140016f3c  add     rsp, 20h
0x140016f40  pop     rdi
0x140016f41  retn
```
