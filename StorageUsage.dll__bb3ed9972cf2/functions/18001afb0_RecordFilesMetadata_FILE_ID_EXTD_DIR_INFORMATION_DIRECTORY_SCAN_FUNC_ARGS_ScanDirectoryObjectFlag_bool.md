# RecordFilesMetadata(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001afb0`
- end: `0x18001b150`
- name: `?RecordFilesMetadata@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `416`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x1800050f0`
- `0x1800152d4`
- `0x180018dec`
- `0x18001afb0`
- `0x18001c968`
- `0x18001e310`
- `0x18001f4a0`

## pseudocode

```c
__int64 __fastcall RecordFilesMetadata(__int64 a1, __int64 a2, int a3)
{
  int v5; // r8d
  int v6; // r8d
  const unsigned __int16 *Buffer; // r8
  USHORT Length; // r11
  int v9; // edi
  unsigned __int16 v10; // r11
  __int64 v11; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // edx
  __int64 v15; // r8
  unsigned int v16; // eax
  struct _UNICODE_STRING v17; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 v18[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[26]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = a3 - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( v6 )
    {
      if ( v6 == 12 )
        WriteFilesMetadataBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
      return 0;
    }
    v17 = 0;
    if ( (unsigned int)FindFileExtension((struct _FILE_ID_EXTD_DIR_INFORMATION *)a1, &v17) == 1168 )
    {
      Buffer = L"<NoExt>";
      Length = 14;
    }
    else
    {
      Length = v17.Length;
      if ( (v17.Length & 0xFFFEu) <= 0x28 )
      {
        Buffer = v17.Buffer;
      }
      else
      {
        Buffer = L"<LongExt>";
        Length = 18;
      }
    }
    memset(v19, 0, sizeof(v19));
    *(_OWORD *)v18 = 0;
    v9 = StringCchCopyNW(v18, 0x15u, Buffer, (unsigned __int64)Length >> 1);
    if ( v9 < 0 )
    {
      v11 = 2129;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
        (const char *)(unsigned int)v9,
        *(int *)&v17.Length);
      return (unsigned int)v9;
    }
    v13 = *(unsigned __int16 *)(a2 + 162);
    v14 = v10 + 6;
    v15 = 2147942522LL;
    if ( v14 <= v13 )
      v16 = v13 < v14 + *(unsigned __int16 *)(a2 + 160) ? 0x8007007A : 0;
    else
      v16 = -2147024785;
    if ( *(_WORD *)(a2 + 152) >= 0x7D0u || v16 == -2147024774 )
      WriteFilesMetadataBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
    v9 = CopyBuffer((struct _UNICODE_STRING *)(a2 + 160), v18, v15, 0x14u);
    if ( v9 < 0 )
    {
      v11 = 2144;
      goto LABEL_12;
    }
    *(_QWORD *)(*(_QWORD *)(a2 + 176) + 8LL * (unsigned __int16)(*(_WORD *)(a2 + 152))++) = *(_QWORD *)(a1 + 40);
  }
  else
  {
    ++*(_WORD *)(a2 + 154);
  }
  return 0;
}

```

## disassembly

```asm
0x18001afb0  mov     [rsp+arg_10], rbx
0x18001afb5  mov     [rsp+arg_18], rsi
0x18001afba  push    rdi
0x18001afbb  sub     rsp, 70h
0x18001afbf  mov     rax, cs:__security_cookie
0x18001afc6  xor     rax, rsp
0x18001afc9  mov     [rsp+78h+var_18], rax
0x18001afce  mov     rbx, rdx
0x18001afd1  mov     rsi, rcx
0x18001afd4  sub     r8d, 1
0x18001afd8  jz      loc_18001B128
0x18001afde  sub     r8d, 3
0x18001afe2  jz      short loc_18001AFFB
0x18001afe4  cmp     r8d, 0Ch
0x18001afe8  jnz     loc_18001B12F
0x18001afee  mov     rcx, rdx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001aff1  call    ?WriteFilesMetadataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteFilesMetadataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001aff6  jmp     loc_18001B12F
0x18001affb  xorps   xmm0, xmm0
0x18001affe  lea     rdx, [rsp+78h+var_58]; struct _UNICODE_STRING *
0x18001b003  movups  xmmword ptr [rsp+78h+var_58.Length], xmm0; int
0x18001b008  call    ?FindFileExtension@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAU_UNICODE_STRING@@@Z; FindFileExtension(_FILE_ID_EXTD_DIR_INFORMATION *,_UNICODE_STRING *)
0x18001b00d  cmp     eax, 490h
0x18001b012  jnz     short loc_18001B023
0x18001b014  mov     r8, cs:off_18002F8C8; "<NoExt>"
0x18001b01b  mov     r11d, 0Eh
0x18001b021  jmp     short loc_18001B04F
0x18001b023  movzx   r11d, [rsp+78h+var_58.Length]
0x18001b029  mov     ecx, 0FFFEh
0x18001b02e  movzx   eax, r11w
0x18001b032  and     ax, cx
0x18001b035  cmp     ax, 28h ; '('
0x18001b039  jbe     short loc_18001B04A
0x18001b03b  mov     r8, cs:off_18002F8B8; "<LongExt>"
0x18001b042  mov     r11d, 12h
0x18001b048  jmp     short loc_18001B04F
0x18001b04a  mov     r8, [rsp+78h+var_58.Buffer]; unsigned __int16 *
0x18001b04f  xorps   xmm0, xmm0
0x18001b052  movzx   r9d, r11w
0x18001b056  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x18001b05b  shr     r9, 1; unsigned __int64
0x18001b05e  lea     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x18001b063  mov     edx, 15h; unsigned __int64
0x18001b068  movups  xmmword ptr [rsp+78h+var_38+0Ah], xmm0
0x18001b06d  movups  xmmword ptr [rsp+78h+var_48], xmm0
0x18001b072  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001b077  mov     edi, eax
0x18001b079  test    eax, eax
0x18001b07b  jns     short loc_18001B09D
0x18001b07d  mov     edx, 851h; void *
0x18001b082  mov     rcx, [rsp+78h]; this
0x18001b087  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001b08e  mov     r9d, edi; char *
0x18001b091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b096  mov     eax, edi
0x18001b098  jmp     loc_18001B131
0x18001b09d  lea     rdi, [rbx+0A0h]
0x18001b0a4  movzx   edx, r11w
0x18001b0a8  movzx   ecx, word ptr [rdi+2]
0x18001b0ac  add     edx, 6
0x18001b0af  mov     r8d, 8007007Ah
0x18001b0b5  cmp     edx, ecx
0x18001b0b7  jbe     short loc_18001B0BF
0x18001b0b9  lea     eax, [r8-0Bh]
0x18001b0bd  jmp     short loc_18001B0CB
0x18001b0bf  movzx   eax, word ptr [rdi]
0x18001b0c2  add     eax, edx
0x18001b0c4  cmp     ecx, eax
0x18001b0c6  sbb     eax, eax
0x18001b0c8  and     eax, r8d
0x18001b0cb  mov     ecx, 7D0h
0x18001b0d0  cmp     [rbx+98h], cx
0x18001b0d7  jnb     short loc_18001B0DE
0x18001b0d9  cmp     eax, r8d
0x18001b0dc  jnz     short loc_18001B0E6
0x18001b0de  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001b0e1  call    ?WriteFilesMetadataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteFilesMetadataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001b0e6  mov     r9d, 14h; unsigned int
0x18001b0ec  lea     rdx, [rsp+78h+var_48]; unsigned __int16 *
0x18001b0f1  mov     rcx, rdi; struct _UNICODE_STRING *
0x18001b0f4  call    ?CopyBuffer@@YAJPEAU_UNICODE_STRING@@PEBGGK@Z; CopyBuffer(_UNICODE_STRING *,ushort const *,ushort,ulong)
0x18001b0f9  mov     edi, eax
0x18001b0fb  test    eax, eax
0x18001b0fd  jns     short loc_18001B109
0x18001b0ff  mov     edx, 860h
0x18001b104  jmp     loc_18001B082
0x18001b109  movzx   edx, word ptr [rbx+98h]
0x18001b110  mov     rax, [rsi+28h]
0x18001b114  mov     rcx, [rbx+0B0h]
0x18001b11b  mov     [rcx+rdx*8], rax
0x18001b11f  inc     word ptr [rbx+98h]
0x18001b126  jmp     short loc_18001B12F
0x18001b128  inc     word ptr [rdx+9Ah]
0x18001b12f  xor     eax, eax
0x18001b131  mov     rcx, [rsp+78h+var_18]
0x18001b136  xor     rcx, rsp; StackCookie
0x18001b139  call    __security_check_cookie
0x18001b13e  lea     r11, [rsp+78h+var_8]
0x18001b143  mov     rbx, [r11+20h]
0x18001b147  mov     rsi, [r11+28h]
0x18001b14b  mov     rsp, r11
0x18001b14e  pop     rdi
0x18001b14f  retn
```
