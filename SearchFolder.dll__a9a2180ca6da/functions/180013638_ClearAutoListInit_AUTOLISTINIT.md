# ClearAutoListInit(AUTOLISTINIT *)

- ea: `0x180013638`
- end: `0x1800136e1`
- name: `?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z`
- size: `169`
- prototype: `void __fastcall(struct AUTOLISTINIT *)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013e0c`
- `0x18001479c`
- `0x18001ef00`
- `0x1800319f8`
- `0x18003202c`
- `0x180032260`
- `0x180033838`
- `0x180038848`
- `0x18003a608`
- `0x18003e5d0`

## callees

- `0x180011f3c`
- `0x180013638`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013656`

## pseudocode

```c
void __fastcall ClearAutoListInit(struct AUTOLISTINIT *a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  CoTaskMemFree(*((LPVOID *)a1 + 1));
  v2 = *(void **)a1;
  *((_QWORD *)a1 + 1) = 0;
  CoTaskMemFree(v2);
  *(_QWORD *)a1 = 0;
  SafeRelease<IShellItemArray>((__int64 *)a1 + 15);
  SafeRelease<IShellItemArray>((__int64 *)a1 + 16);
  SafeRelease<IShellItemArray>((__int64 *)a1 + 17);
  SafeRelease<IShellItemArray>((__int64 *)a1 + 18);
  v3 = *((_QWORD *)a1 + 14);
  *((_QWORD *)a1 + 14) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)a1 + 19);
  *((_QWORD *)a1 + 19) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  SafeRelease<IShellItemArray>((__int64 *)a1 + 21);
}

```

## disassembly

```asm
0x180013638  push    rbx
0x18001363a  sub     rsp, 20h
0x18001363e  mov     rbx, rcx
0x180013641  mov     rcx, [rcx+8]; pv
0x180013645  call    cs:__imp_CoTaskMemFree
0x18001364b  mov     rcx, [rbx]; pv
0x18001364e  mov     qword ptr [rbx+8], 0
0x180013656  call    cs:__imp_CoTaskMemFree
0x18001365c  lea     rcx, [rbx+78h]
0x180013660  mov     qword ptr [rbx], 0
0x180013667  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18001366c  lea     rcx, [rbx+80h]
0x180013673  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180013678  lea     rcx, [rbx+88h]
0x18001367f  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180013684  lea     rcx, [rbx+90h]
0x18001368b  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180013690  mov     rcx, [rbx+70h]
0x180013694  mov     qword ptr [rbx+70h], 0
0x18001369c  test    rcx, rcx
0x18001369f  jz      short loc_1800136AD
0x1800136a1  mov     rax, [rcx]
0x1800136a4  mov     rax, [rax+10h]
0x1800136a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136ad  mov     rcx, [rbx+98h]
0x1800136b4  mov     qword ptr [rbx+98h], 0
0x1800136bf  test    rcx, rcx
0x1800136c2  jz      short loc_1800136D0
0x1800136c4  mov     rax, [rcx]
0x1800136c7  mov     rax, [rax+10h]
0x1800136cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136d0  lea     rcx, [rbx+0A8h]
0x1800136d7  add     rsp, 20h
0x1800136db  pop     rbx
0x1800136dc  jmp     ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
```
