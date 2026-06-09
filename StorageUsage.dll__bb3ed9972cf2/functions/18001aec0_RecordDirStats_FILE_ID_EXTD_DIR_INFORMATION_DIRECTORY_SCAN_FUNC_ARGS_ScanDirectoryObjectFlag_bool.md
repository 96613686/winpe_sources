# RecordDirStats(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001aec0`
- end: `0x18001af9c`
- name: `?RecordDirStats@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ad40`

## callees

- `0x1800152d4`
- `0x18001aec0`
- `0x18001def0`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall RecordDirStats(__int64 a1, __int64 a2, int a3, unsigned __int8 a4)
{
  unsigned int v7; // ecx
  unsigned int v8; // edx
  int v9; // eax
  unsigned int v10; // esi
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a3 == 8 )
  {
    v7 = *(unsigned __int16 *)(a2 + 98);
    v8 = *(unsigned __int16 *)(a2 + 16LL * a4 + 40) + 6;
    if ( v8 <= v7 )
    {
      if ( *(_WORD *)(a2 + 88) >= 0x3E8u || v8 + *(unsigned __int16 *)(a2 + 96) > v7 )
        WriteDirDataBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
      v9 = CopyPath(a1, a2, 1, a4, 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x656,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
          (const char *)(unsigned int)v9,
          v12);
        return v10;
      }
      *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8LL * (unsigned __int16)(*(_WORD *)(a2 + 88))++) = *(_QWORD *)(a2 + 72);
    }
    else
    {
      ++*(_WORD *)(a2 + 80);
    }
  }
  else if ( a3 == 16 )
  {
    WriteDirDataBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18001aec0  mov     [rsp+arg_0], rbx
0x18001aec5  mov     [rsp+arg_8], rsi
0x18001aeca  push    rdi
0x18001aecb  sub     rsp, 30h
0x18001aecf  movzx   edi, r9b
0x18001aed3  mov     rbx, rdx
0x18001aed6  mov     rsi, rcx
0x18001aed9  cmp     r8d, 8
0x18001aedd  jz      short loc_18001AEF6
0x18001aedf  cmp     r8d, 10h
0x18001aee3  jnz     loc_18001AF8A
0x18001aee9  mov     rcx, rdx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001aeec  call    ?WriteDirDataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteDirDataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001aef1  jmp     loc_18001AF8A
0x18001aef6  movzx   ecx, word ptr [rdx+62h]
0x18001aefa  mov     rax, rdi
0x18001aefd  add     rax, rax
0x18001af00  movzx   edx, word ptr [rdx+rax*8+28h]
0x18001af05  add     edx, 6
0x18001af08  cmp     edx, ecx
0x18001af0a  jbe     short loc_18001AF17
0x18001af0c  mov     edi, 1
0x18001af11  add     [rbx+50h], di
0x18001af15  jmp     short loc_18001AF8A
0x18001af17  mov     eax, 3E8h
0x18001af1c  cmp     [rbx+58h], ax
0x18001af20  jnb     short loc_18001AF2C
0x18001af22  movzx   eax, word ptr [rbx+60h]
0x18001af26  add     eax, edx
0x18001af28  cmp     eax, ecx
0x18001af2a  jbe     short loc_18001AF34
0x18001af2c  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001af2f  call    ?WriteDirDataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteDirDataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001af34  mov     r9b, dil
0x18001af37  mov     qword ptr [rsp+38h+var_18], 0; int
0x18001af40  mov     edi, 1
0x18001af45  mov     rdx, rbx
0x18001af48  mov     r8d, edi
0x18001af4b  mov     rcx, rsi
0x18001af4e  call    ?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z; CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)
0x18001af53  mov     esi, eax
0x18001af55  test    eax, eax
0x18001af57  jns     short loc_18001AF76
0x18001af59  mov     rcx, [rsp+38h]; this
0x18001af5e  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001af65  mov     r9d, eax; char *
0x18001af68  mov     edx, 656h; void *
0x18001af6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af72  mov     eax, esi
0x18001af74  jmp     short loc_18001AF8C
0x18001af76  movzx   edx, word ptr [rbx+58h]
0x18001af7a  mov     rcx, [rbx+70h]
0x18001af7e  mov     rax, [rbx+48h]
0x18001af82  mov     [rcx+rdx*8], rax
0x18001af86  add     [rbx+58h], di
0x18001af8a  xor     eax, eax
0x18001af8c  mov     rbx, [rsp+38h+arg_0]
0x18001af91  mov     rsi, [rsp+38h+arg_8]
0x18001af96  add     rsp, 30h
0x18001af9a  pop     rdi
0x18001af9b  retn
```
