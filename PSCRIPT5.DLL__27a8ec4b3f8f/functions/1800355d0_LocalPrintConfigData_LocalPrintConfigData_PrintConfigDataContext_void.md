# LocalPrintConfigData::LocalPrintConfigData(PrintConfigDataContext &,void *)

- ea: `0x1800355d0`
- end: `0x1800356f8`
- name: `??0LocalPrintConfigData@@AEAA@AEAVPrintConfigDataContext@@PEAX@Z`
- size: `296`
- prototype: `LocalPrintConfigData *__fastcall(LocalPrintConfigData *__hidden this, struct PrintConfigDataContext *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180035968`

## callees

- `0x1800355d0`
- `0x180037500`
- `0x180037634`

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
  ParseDriverInfo(v5, (LPWSTR *)this + 2);
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
0x1800355d0  mov     [rsp+arg_0], rbx
0x1800355d5  mov     [rsp+arg_8], rsi
0x1800355da  push    rdi
0x1800355db  sub     rsp, 20h
0x1800355df  lea     rax, ??_7LocalPrintConfigData@@6B@; const LocalPrintConfigData::`vftable'
0x1800355e6  mov     qword ptr [rcx+60h], 0
0x1800355ee  mov     [rcx], rax
0x1800355f1  mov     rbx, rcx
0x1800355f4  mov     qword ptr [rcx+68h], 0
0x1800355fc  mov     [rcx+70h], r8
0x180035600  mov     dword ptr [rcx+78h], 0
0x180035607  mov     qword ptr [rcx+80h], 0
0x180035612  mov     qword ptr [rcx+88h], 0
0x18003561d  mov     qword ptr [rcx+298h], 0
0x180035628  mov     dword ptr [rcx+0D18h], 0
0x180035632  mov     rax, [rdx+8]
0x180035636  test    rax, rax
0x180035639  jz      short loc_180035665
0x18003563b  mov     eax, [rax+0A8h]
0x180035641  mov     [rcx+78h], eax
0x180035644  mov     rax, [rdx+8]
0x180035648  mov     rcx, [rax+0A0h]
0x18003564f  mov     [rbx+80h], rcx
0x180035656  mov     rax, [rdx+8]
0x18003565a  mov     rcx, [rax+68h]
0x18003565e  mov     [rbx+88h], rcx
0x180035665  mov     rcx, [rdx+8]
0x180035669  test    rcx, rcx
0x18003566c  jnz     short loc_180035671
0x18003566e  mov     rcx, [rdx]; struct _DRIVER_INFO_3W *
0x180035671  mov     qword ptr [rdx], 0
0x180035678  mov     qword ptr [rdx+8], 0
0x180035680  lea     rdx, [rbx+10h]; struct DriverInfoFiles *
0x180035684  mov     [rbx+8], rcx
0x180035688  call    ?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z; ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)
0x18003568d  mov     rcx, [rbx+28h]; lpFileName
0x180035691  test    rcx, rcx
0x180035694  jz      short loc_1800356A5
0x180035696  lea     rdx, [rbx+60h]; struct V4ManifestFile **
0x18003569a  call    ?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z; V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)
0x18003569f  mov     [rbx+0D18h], eax
0x1800356a5  cmp     dword ptr [rbx+0D18h], 0
0x1800356ac  jl      short loc_1800356C6
0x1800356ae  mov     rcx, [rbx+48h]; lpFileName
0x1800356b2  test    rcx, rcx
0x1800356b5  jz      short loc_1800356C6
0x1800356b7  lea     rdx, [rbx+68h]; struct V4ManifestFile **
0x1800356bb  call    ?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z; V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)
0x1800356c0  mov     [rbx+0D18h], eax
0x1800356c6  mov     rsi, [rsp+28h+arg_8]
0x1800356cb  xor     eax, eax
0x1800356cd  mov     [rbx+2A0h], ax
0x1800356d4  mov     [rbx+4A8h], ax
0x1800356db  mov     [rbx+6B0h], ax
0x1800356e2  mov     [rbx+8B8h], ax
0x1800356e9  mov     rax, rbx
0x1800356ec  mov     rbx, [rsp+28h+arg_0]
0x1800356f1  add     rsp, 20h
0x1800356f5  pop     rdi
0x1800356f6  retn
```
