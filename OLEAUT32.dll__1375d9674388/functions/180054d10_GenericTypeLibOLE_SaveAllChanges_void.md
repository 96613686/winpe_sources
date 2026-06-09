# GenericTypeLibOLE::SaveAllChanges(void)

- ea: `0x180054d10`
- end: `0x180054eda`
- name: `?SaveAllChanges@GenericTypeLibOLE@@UEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(GenericTypeLibOLE *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800228e0`
- `0x18003e360`
- `0x18004d01c`
- `0x180052a74`
- `0x180053770`
- `0x180054d10`
- `0x180054ee0`
- `0x18005bba8`
- `0x18005d634`
- `0x18005dbbc`
- `0x180063130`
- `0x1800679e8`
- `0x18009a624`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x180054eb8`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x180054eb8`

## pseudocode

```c
__int64 __fastcall GenericTypeLibOLE::SaveAllChanges(GenericTypeLibOLE *this)
{
  DOCSTR_MGR *v1; // r13
  __int64 result; // rax
  unsigned int i; // esi
  __int64 v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // r9d
  unsigned int v8; // r12d
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  void *v11; // rcx
  struct IStorage *v12; // rbx
  unsigned int v13; // esi
  unsigned int v14; // edx
  const WCHAR *v15; // rax
  char *FileName; // [rsp+70h] [rbp+48h] BYREF
  unsigned int v17; // [rsp+78h] [rbp+50h] BYREF
  void *Src; // [rsp+80h] [rbp+58h] BYREF
  struct IStorage *v19; // [rsp+88h] [rbp+60h] BYREF

  v1 = (GenericTypeLibOLE *)((char *)this + 1712);
  v19 = 0;
  LODWORD(FileName) = 0;
  Src = 0;
  v17 = 0;
  result = DOCSTR_MGR::ProcessDocStrings((GenericTypeLibOLE *)((char *)this + 1712));
  if ( (int)result >= 0 )
  {
    for ( i = 0; i < *((unsigned __int16 *)this + 116); ++i )
    {
      if ( (unsigned int)GEN_DTINFO::IsDualDispinterface(*(GEN_DTINFO **)(*((_QWORD *)this + 3)
                                                                        + 80LL * (unsigned __int16)i
                                                                        + 8)) )
        v5 = *(_QWORD *)(v5 + 48);
      result = TYPE_DATA::UpdateDocStrings((TYPE_DATA *)(*(_QWORD *)(*(_QWORD *)(v5 + 56) + 168LL) + 8LL));
      if ( (int)result < 0 )
        return result;
      v6 = *(_DWORD *)(*((_QWORD *)this + 3) + 80LL * (unsigned __int16)i + 44);
      if ( v6 != 0xFFFF )
      {
        result = DOCSTR_MGR::GetEncodedDocStrOfHst(v1, v6, (char **)&Src, (unsigned int *)&FileName);
        if ( (int)result < 0 )
          return result;
        v8 = (unsigned int)FileName;
        if ( (unsigned int)FileName > 0xFFFF )
          v8 = 0xFFFF;
        LODWORD(FileName) = v8;
        v9 = BLK_MGR::AllocChunk2((GenericTypeLibOLE *)((char *)this + 64), &v17, v8, v7);
        if ( v9 )
        {
          MemFree(Src);
          return v9;
        }
        v10 = v17;
        memcpy_0((void *)(*((_QWORD *)this + 8) + v17), Src, v8);
        v11 = Src;
        *(_WORD *)(*((_QWORD *)this + 3) + 80LL * (unsigned __int16)i + 40) = v8;
        *(_DWORD *)(*((_QWORD *)this + 3) + 80LL * (unsigned __int16)i + 44) = v10;
        MemFree(v11);
      }
    }
    result = GenericTypeLibOLE::GetStorage((GenericTypeLibOLE *)((char *)this - 8), 0x1012u, &v19);
    if ( (int)result >= 0 )
    {
      v12 = v19;
      v13 = GenericTypeLibOLE::SaveOrCopyChanges((GenericTypeLibOLE *)((char *)this - 8), v19);
      if ( !v13 )
        v13 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD))v12->lpVtbl->Commit)(v12, 0);
      ((void (__fastcall *)(struct IStorage *))v12->lpVtbl->Release)(v12);
      if ( v13 )
      {
        v14 = *((_DWORD *)this + 40);
        FileName = 0;
        v15 = GenericTypeLibOLE::QszOfHsz((GenericTypeLibOLE *)((char *)this - 8), v14);
        if ( (int)ConvertStringToA(v15, &FileName) >= 0 )
        {
          remove(FileName);
          ConvertStringFree(FileName);
        }
      }
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180054d10  push    rbp
0x180054d12  push    rbx
0x180054d13  push    rsi
0x180054d14  push    rdi
0x180054d15  push    r12
0x180054d17  push    r13
0x180054d19  push    r14
0x180054d1b  push    r15
0x180054d1d  mov     rbp, rsp
0x180054d20  sub     rsp, 28h
0x180054d24  xor     r12d, r12d
0x180054d27  lea     r13, [rcx+6B0h]
0x180054d2e  mov     rdi, rcx
0x180054d31  mov     [rbp+arg_18], r12
0x180054d35  mov     rcx, r13; this
0x180054d38  mov     dword ptr [rbp+FileName], r12d
0x180054d3c  mov     [rbp+Src], r12
0x180054d40  mov     [rbp+arg_8], r12d
0x180054d44  call    ?ProcessDocStrings@DOCSTR_MGR@@QEAAJXZ; DOCSTR_MGR::ProcessDocStrings(void)
0x180054d49  test    eax, eax
0x180054d4b  js      loc_180054EC9
0x180054d51  mov     esi, r12d
0x180054d54  lea     r14, [rdi-8]
0x180054d58  mov     ebx, 0FFFFh
0x180054d5d  movzx   eax, word ptr [rdi+0E8h]
0x180054d64  cmp     esi, eax
0x180054d66  jnb     loc_180054E42
0x180054d6c  movzx   eax, si
0x180054d6f  lea     r15, [rax+rax*4]
0x180054d73  mov     rax, [r14+20h]
0x180054d77  add     r15, r15
0x180054d7a  mov     rcx, [rax+r15*8+8]; this
0x180054d7f  call    ?IsDualDispinterface@GEN_DTINFO@@QEAAHXZ; GEN_DTINFO::IsDualDispinterface(void)
0x180054d84  test    eax, eax
0x180054d86  jz      short loc_180054D8C
0x180054d88  mov     rcx, [rcx+30h]
0x180054d8c  mov     rax, [rcx+38h]
0x180054d90  mov     rcx, [rax+0A8h]
0x180054d97  add     rcx, 8; this
0x180054d9b  call    ?UpdateDocStrings@TYPE_DATA@@QEAAJXZ; TYPE_DATA::UpdateDocStrings(void)
0x180054da0  test    eax, eax
0x180054da2  js      loc_180054EC9
0x180054da8  mov     rax, [rdi+18h]
0x180054dac  mov     edx, [rax+r15*8+2Ch]; unsigned int
0x180054db1  cmp     edx, ebx
0x180054db3  jz      short loc_180054E2B
0x180054db5  lea     r9, [rbp+FileName]; unsigned int *
0x180054db9  mov     rcx, r13; this
0x180054dbc  lea     r8, [rbp+Src]; char **
0x180054dc0  call    ?GetEncodedDocStrOfHst@DOCSTR_MGR@@QEAAJIPEAPEADPEAI@Z; DOCSTR_MGR::GetEncodedDocStrOfHst(uint,char * *,uint *)
0x180054dc5  test    eax, eax
0x180054dc7  js      loc_180054EC9
0x180054dcd  mov     r12d, dword ptr [rbp+FileName]
0x180054dd1  lea     rcx, [rdi+40h]; this
0x180054dd5  cmp     r12d, ebx
0x180054dd8  lea     rdx, [rbp+arg_8]; unsigned int *
0x180054ddc  cmova   r12d, ebx
0x180054de0  mov     r8d, r12d; unsigned int
0x180054de3  mov     dword ptr [rbp+FileName], r12d
0x180054de7  call    ?AllocChunk2@BLK_MGR@@AEAAJPEAIII@Z; BLK_MGR::AllocChunk2(uint *,uint,uint)
0x180054dec  mov     ebx, eax
0x180054dee  test    eax, eax
0x180054df0  jnz     short loc_180054E32
0x180054df2  mov     ebx, [rbp+arg_8]
0x180054df5  mov     rdx, [rbp+Src]; Src
0x180054df9  mov     ecx, ebx
0x180054dfb  add     rcx, [rdi+40h]; void *
0x180054dff  mov     r8d, r12d; Size
0x180054e02  call    memcpy_0
0x180054e07  mov     rax, [rdi+18h]
0x180054e0b  mov     rcx, [rbp+Src]
0x180054e0f  mov     [rax+r15*8+28h], r12w
0x180054e15  mov     rax, [rdi+18h]
0x180054e19  mov     [rax+r15*8+2Ch], ebx
0x180054e1e  call    MemFree
0x180054e23  xor     r12d, r12d
0x180054e26  mov     ebx, 0FFFFh
0x180054e2b  inc     esi
0x180054e2d  jmp     loc_180054D5D
0x180054e32  mov     rcx, [rbp+Src]
0x180054e36  call    MemFree
0x180054e3b  mov     eax, ebx
0x180054e3d  jmp     loc_180054EC9
0x180054e42  lea     r8, [rbp+arg_18]; struct IStorage **
0x180054e46  mov     edx, 1012h; unsigned int
0x180054e4b  mov     rcx, r14; this
0x180054e4e  call    ?GetStorage@GenericTypeLibOLE@@QEAAJKPEAPEAUIStorage@@@Z; GenericTypeLibOLE::GetStorage(ulong,IStorage * *)
0x180054e53  test    eax, eax
0x180054e55  js      short loc_180054EC9
0x180054e57  mov     rbx, [rbp+arg_18]
0x180054e5b  mov     rcx, r14; this
0x180054e5e  mov     rdx, rbx; struct IStorage *
0x180054e61  call    ?SaveOrCopyChanges@GenericTypeLibOLE@@QEAAJPEAUIStorage@@H@Z; GenericTypeLibOLE::SaveOrCopyChanges(IStorage *,int)
0x180054e66  mov     esi, eax
0x180054e68  test    eax, eax
0x180054e6a  jnz     short loc_180054E7F
0x180054e6c  mov     rax, [rbx]
0x180054e6f  xor     edx, edx
0x180054e71  mov     rcx, rbx
0x180054e74  mov     rax, [rax+48h]
0x180054e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e7d  mov     esi, eax
0x180054e7f  mov     rax, [rbx]
0x180054e82  mov     rcx, rbx
0x180054e85  mov     rax, [rax+10h]
0x180054e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e8e  test    esi, esi
0x180054e90  jz      short loc_180054EC7
0x180054e92  mov     edx, [rdi+0A0h]; unsigned int
0x180054e98  mov     rcx, r14; this
0x180054e9b  mov     [rbp+FileName], r12
0x180054e9f  call    ?QszOfHsz@GenericTypeLibOLE@@IEAAPEAGI@Z; GenericTypeLibOLE::QszOfHsz(uint)
0x180054ea4  mov     rcx, rax; lpWideCharStr
0x180054ea7  lea     rdx, [rbp+FileName]; char **
0x180054eab  call    ?ConvertStringToA@@YAJPEBGPEAPEAD@Z; ConvertStringToA(ushort const *,char * *)
0x180054eb0  test    eax, eax
0x180054eb2  js      short loc_180054EC7
0x180054eb4  mov     rcx, [rbp+FileName]; FileName
0x180054eb8  call    cs:__imp_remove
0x180054ebe  mov     rcx, [rbp+FileName]; char *
0x180054ec2  call    ?ConvertStringFree@@YAXPEAD@Z; ConvertStringFree(char *)
0x180054ec7  mov     eax, esi
0x180054ec9  add     rsp, 28h
0x180054ecd  pop     r15
0x180054ecf  pop     r14
0x180054ed1  pop     r13
0x180054ed3  pop     r12
0x180054ed5  pop     rdi
0x180054ed6  pop     rsi
0x180054ed7  pop     rbx
0x180054ed8  pop     rbp
0x180054ed9  retn
```
