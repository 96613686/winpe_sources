# SuAutoRepairSpaces(_GUID const *)

- ea: `0x140016900`
- end: `0x14001698b`
- name: `?SuAutoRepairSpaces@@YAXPEBU_GUID@@@Z`
- size: `139`
- prototype: `void __fastcall(const struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001913c`
- `0x140019310`
- `0x140019498`
- `0x140019804`

## callees

- `0x140012e84`
- `0x140013514`
- `0x140016900`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001697a`
- `KERNEL32!LocalFree` at `0x14001697a`

## pseudocode

```c
void __fastcall SuAutoRepairSpaces(struct _GUID *a1)
{
  int SpaceIds; // eax
  unsigned int *v3; // rbx
  __int64 v4; // xmm0_8
  int v5; // eax
  unsigned int v6; // edi
  _OWORD v7[2]; // [rsp+20h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  memset((char *)v7 + 4, 0, 28);
  hMem = 0;
  SpaceIds = SuGetSpaceIds(a1, (struct _SP_IDS **)&hMem);
  v3 = (unsigned int *)hMem;
  if ( SpaceIds )
  {
    v4 = *(_QWORD *)&a1->Data2;
    LODWORD(v7[0]) = a1->Data1;
    v5 = *(_DWORD *)&a1->Data4[4];
    v6 = 0;
    *(_QWORD *)((char *)v7 + 4) = v4;
    HIDWORD(v7[0]) = v5;
    if ( *(_DWORD *)hMem )
    {
      do
      {
        v7[1] = *(_OWORD *)&v3[4 * v6 + 1];
        SuRepairSpace(v7);
        ++v6;
      }
      while ( v6 < *v3 );
    }
  }
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x140016900  mov     [rsp+arg_0], rbx
0x140016905  push    rdi
0x140016906  sub     rsp, 40h
0x14001690a  xorps   xmm0, xmm0
0x14001690d  lea     rdx, [rsp+48h+hMem]; struct _SP_IDS **
0x140016912  xor     eax, eax
0x140016914  mov     rdi, rcx
0x140016917  movups  xmmword ptr [rsp+48h+var_24], xmm0
0x14001691c  mov     [rsp+48h+hMem], rax
0x140016921  movups  xmmword ptr [rsp+48h+var_24+0Ch], xmm0
0x140016926  call    ?SuGetSpaceIds@@YAHPEAU_GUID@@PEAPEAU_SP_IDS@@@Z; SuGetSpaceIds(_GUID *,_SP_IDS * *)
0x14001692b  mov     rbx, [rsp+48h+hMem]
0x140016930  test    eax, eax
0x140016932  jz      short loc_140016972
0x140016934  mov     eax, [rdi]
0x140016936  movsd   xmm0, qword ptr [rdi+4]
0x14001693b  mov     [rsp+48h+var_28], eax
0x14001693f  mov     eax, [rdi+0Ch]
0x140016942  xor     edi, edi
0x140016944  movsd   qword ptr [rsp+48h+var_24], xmm0
0x14001694a  mov     dword ptr [rsp+48h+var_24+8], eax
0x14001694e  cmp     [rbx], edi
0x140016950  jbe     short loc_140016972
0x140016952  mov     eax, edi
0x140016954  lea     rcx, [rsp+48h+var_28]
0x140016959  add     rax, rax
0x14001695c  movups  xmm0, xmmword ptr [rbx+rax*8+4]
0x140016961  movdqu  xmmword ptr [rsp+48h+var_24+0Ch], xmm0
0x140016967  call    ?SuRepairSpace@@YAHPEAU_SP_ID@@W4_SC_REPAIR_PHASE@@@Z; SuRepairSpace(_SP_ID *,_SC_REPAIR_PHASE)
0x14001696c  inc     edi
0x14001696e  cmp     edi, [rbx]
0x140016970  jb      short loc_140016952
0x140016972  test    rbx, rbx
0x140016975  jz      short loc_140016980
0x140016977  mov     rcx, rbx; hMem
0x14001697a  call    cs:__imp_LocalFree
0x140016980  mov     rbx, [rsp+48h+arg_0]
0x140016985  add     rsp, 40h
0x140016989  pop     rdi
0x14001698a  retn
```
