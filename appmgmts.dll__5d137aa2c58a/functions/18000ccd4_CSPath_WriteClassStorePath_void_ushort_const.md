# CSPath::WriteClassStorePath(void *,ushort const *)

- ea: `0x18000ccd4`
- end: `0x18000cd59`
- name: `?WriteClassStorePath@CSPath@@QEAAKPEAXPEBG@Z`
- size: `133`
- prototype: `DWORD __fastcall(CSPath *this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cb98`

## callees

- `0x18000cc10`
- `0x18000ccd4`
- `0x18000cd60`
- `0x180011268`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd46`

## pseudocode

```c
DWORD __fastcall CSPath::WriteClassStorePath(CSPath *this, void *a2, const unsigned __int16 *a3)
{
  DWORD result; // eax
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  int v8; // [rsp+34h] [rbp+Ch]
  HLOCAL hMem; // [rsp+48h] [rbp+20h] BYREF

  v8 = HIDWORD(this);
  hMem = 0;
  v7 = 0;
  result = GetScriptDirPath(a2, 12, (unsigned __int16 **)&hMem, &v7);
  if ( !result )
  {
    v5 = StringCchCatW((unsigned __int16 *)hMem, v7, L"AppMgmt.ini");
    v6 = (unsigned __int16)v5;
    if ( v5 >= 0 )
      v6 = 0;
    if ( !v6 )
      v6 = CSPath::WriteClassStorePathToFile(0, (const unsigned __int16 *)hMem, a3);
    LocalFree(hMem);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000ccd4  mov     rax, rsp
0x18000ccd7  mov     [rax+10h], rbx
0x18000ccdb  mov     [rax+8], rcx
0x18000ccdf  push    rsi
0x18000cce0  sub     rsp, 20h
0x18000cce4  mov     rsi, r8
0x18000cce7  mov     qword ptr [rax+20h], 0
0x18000ccef  mov     rcx, rdx; void *
0x18000ccf2  mov     dword ptr [rax+8], 0
0x18000ccf9  lea     r8, [rax+20h]; unsigned __int16 **
0x18000ccfd  mov     edx, 0Ch; unsigned int
0x18000cd02  lea     r9, [rax+8]; unsigned int *
0x18000cd06  call    ?GetScriptDirPath@@YAKPEAXKPEAPEAGPEAK@Z; GetScriptDirPath(void *,ulong,ushort * *,ulong *)
0x18000cd0b  test    eax, eax
0x18000cd0d  jnz     short loc_18000CD4E
0x18000cd0f  mov     edx, dword ptr [rsp+28h+arg_0]; unsigned __int64
0x18000cd13  lea     r8, aAppmgmtIni_0; "AppMgmt.ini"
0x18000cd1a  mov     rcx, [rsp+28h+hMem]; unsigned __int16 *
0x18000cd1f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd24  xor     ecx, ecx; this
0x18000cd26  movzx   ebx, ax
0x18000cd29  test    eax, eax
0x18000cd2b  cmovns  ebx, ecx
0x18000cd2e  test    ebx, ebx
0x18000cd30  jnz     short loc_18000CD41
0x18000cd32  mov     rdx, [rsp+28h+hMem]; unsigned __int16 *
0x18000cd37  mov     r8, rsi; unsigned __int16 *
0x18000cd3a  call    ?WriteClassStorePathToFile@CSPath@@AEAAJPEBG0@Z; CSPath::WriteClassStorePathToFile(ushort const *,ushort const *)
0x18000cd3f  mov     ebx, eax
0x18000cd41  mov     rcx, [rsp+28h+hMem]; hMem
0x18000cd46  call    cs:__imp_LocalFree
0x18000cd4c  mov     eax, ebx
0x18000cd4e  mov     rbx, [rsp+28h+arg_8]
0x18000cd53  add     rsp, 20h
0x18000cd57  pop     rsi
0x18000cd58  retn
```
