# LocalPrintConfigData::LocalPrintConfigData(PrintConfigDataContext &,void *)

- ea: `0x180033ecc`
- end: `0x180033ff3`
- name: `??0LocalPrintConfigData@@AEAA@AEAVPrintConfigDataContext@@PEAX@Z`
- size: `295`
- prototype: `LocalPrintConfigData *__fastcall(LocalPrintConfigData *__hidden this, struct PrintConfigDataContext *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180034258`

## callees

- `0x180033ecc`
- `0x180035d1c`
- `0x180035e3c`

## pseudocode

```c
LocalPrintConfigData *__fastcall LocalPrintConfigData::LocalPrintConfigData(
        LocalPrintConfigData *this,
        struct PrintConfigDataContext *a2,
        void *a3)
{
  __int64 v4; // rax
  struct _DRIVER_INFO_3W *v5; // rcx
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx

  *((_QWORD *)this + 12) = 0;
  *(_QWORD *)this = &LocalPrintConfigData::`vftable';
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = a3;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_DWORD *)this + 838) = 0;
  v4 = *((_QWORD *)a2 + 1);
  if ( v4 )
  {
    *((_DWORD *)this + 30) = *(_DWORD *)(v4 + 168);
    *((_QWORD *)this + 16) = *(_QWORD *)(*((_QWORD *)a2 + 1) + 160LL);
    *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)a2 + 1) + 104LL);
  }
  v5 = (struct _DRIVER_INFO_3W *)*((_QWORD *)a2 + 1);
  if ( !v5 )
    v5 = *(struct _DRIVER_INFO_3W **)a2;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)this + 1) = v5;
  ParseDriverInfo(v5, (const wchar_t **)this + 2);
  v6 = (const WCHAR *)*((_QWORD *)this + 5);
  if ( v6 )
    *((_DWORD *)this + 838) = V4ManifestFile::ParseManifestFile(v6, (struct V4ManifestFile **)this + 12);
  if ( *((int *)this + 838) >= 0 )
  {
    v7 = (const WCHAR *)*((_QWORD *)this + 9);
    if ( v7 )
      *((_DWORD *)this + 838) = V4ManifestFile::ParseManifestFile(v7, (struct V4ManifestFile **)this + 13);
  }
  *((_WORD *)this + 336) = 0;
  *((_WORD *)this + 596) = 0;
  *((_WORD *)this + 856) = 0;
  *((_WORD *)this + 1116) = 0;
  return this;
}

```

## disassembly

```asm
0x180033ecc  mov     [rsp+arg_0], rbx
0x180033ed1  mov     [rsp+arg_8], rsi
0x180033ed6  push    rdi
0x180033ed7  sub     rsp, 20h
0x180033edb  lea     rax, ??_7LocalPrintConfigData@@6B@; const LocalPrintConfigData::`vftable'
0x180033ee2  mov     qword ptr [rcx+60h], 0
0x180033eea  mov     [rcx], rax
0x180033eed  mov     rbx, rcx
0x180033ef0  mov     qword ptr [rcx+68h], 0
0x180033ef8  mov     [rcx+70h], r8
0x180033efc  mov     dword ptr [rcx+78h], 0
0x180033f03  mov     qword ptr [rcx+80h], 0
0x180033f0e  mov     qword ptr [rcx+88h], 0
0x180033f19  mov     qword ptr [rcx+298h], 0
0x180033f24  mov     dword ptr [rcx+0D18h], 0
0x180033f2e  mov     rax, [rdx+8]
0x180033f32  test    rax, rax
0x180033f35  jz      short loc_180033F61
0x180033f37  mov     eax, [rax+0A8h]
0x180033f3d  mov     [rcx+78h], eax
0x180033f40  mov     rax, [rdx+8]
0x180033f44  mov     rcx, [rax+0A0h]
0x180033f4b  mov     [rbx+80h], rcx
0x180033f52  mov     rax, [rdx+8]
0x180033f56  mov     rcx, [rax+68h]
0x180033f5a  mov     [rbx+88h], rcx
0x180033f61  mov     rcx, [rdx+8]
0x180033f65  test    rcx, rcx
0x180033f68  jnz     short loc_180033F6D
0x180033f6a  mov     rcx, [rdx]; struct _DRIVER_INFO_3W *
0x180033f6d  mov     qword ptr [rdx], 0
0x180033f74  mov     qword ptr [rdx+8], 0
0x180033f7c  lea     rdx, [rbx+10h]; struct DriverInfoFiles *
0x180033f80  mov     [rbx+8], rcx
0x180033f84  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x180033f89  mov     rcx, [rbx+28h]; lpFileName
0x180033f8d  test    rcx, rcx
0x180033f90  jz      short loc_180033FA1
0x180033f92  lea     rdx, [rbx+60h]; struct V4ManifestFile **
0x180033f96  call    ?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z; V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)
0x180033f9b  mov     [rbx+0D18h], eax
0x180033fa1  cmp     dword ptr [rbx+0D18h], 0
0x180033fa8  jl      short loc_180033FC2
0x180033faa  mov     rcx, [rbx+48h]; lpFileName
0x180033fae  test    rcx, rcx
0x180033fb1  jz      short loc_180033FC2
0x180033fb3  lea     rdx, [rbx+68h]; struct V4ManifestFile **
0x180033fb7  call    ?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z; V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)
0x180033fbc  mov     [rbx+0D18h], eax
0x180033fc2  mov     rsi, [rsp+28h+arg_8]
0x180033fc7  xor     eax, eax
0x180033fc9  mov     [rbx+2A0h], ax
0x180033fd0  mov     [rbx+4A8h], ax
0x180033fd7  mov     [rbx+6B0h], ax
0x180033fde  mov     [rbx+8B8h], ax
0x180033fe5  mov     rax, rbx
0x180033fe8  mov     rbx, [rsp+28h+arg_0]
0x180033fed  add     rsp, 20h
0x180033ff1  pop     rdi
0x180033ff2  retn
```
