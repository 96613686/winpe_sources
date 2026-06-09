# DPFreeDeployableUpdateData(void *)

- ea: `0x180022790`
- end: `0x180022859`
- name: `?DPFreeDeployableUpdateData@@YAXPEAX@Z`
- size: `201`
- prototype: `void __fastcall(void *)`
- caller_count: `19`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180023220`
- `0x180023cb0`
- `0x180023fdc`
- `0x18002559c`
- `0x1800255c0`
- `0x1800257a8`
- `0x18002ac0c`
- `0x18002b304`
- `0x18002b4c0`
- `0x18002c5a8`
- `0x18002d3d0`
- `0x18002f900`
- `0x180030988`
- `0x180030d74`
- `0x1800330b8`
- `0x18003672c`
- `0x180036dc8`
- `0x180036e50`
- `0x180036eb4`

## callees

- `0x18000c14c`
- `0x180022790`
- `0x18004d3e4`
- `0x18004d4dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022808`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022808`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022817`
- `OLEAUT32!__imp_SysFreeString` at `0x1800227f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800227f1`

## pseudocode

```c
void __fastcall DPFreeDeployableUpdateData(char *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  struct tagMatchingUpdate *v5; // rcx

  if ( !a1 )
    return;
  switch ( *(_DWORD *)a1 )
  {
    case 1:
      v5 = (struct tagMatchingUpdate *)(a1 + 8);
      if ( v5 )
        FreeObject(v5, 1);
      return;
    case 2:
      DsqFreeObject((struct tagDSUpdateMetadata *)(a1 + 8), 1u);
      return;
    case 3:
      DsqFreeObject((struct tagDSDeployment *)(a1 + 8));
      return;
    case 4:
      v4 = (void *)*((_QWORD *)a1 + 1);
      if ( v4 )
        CoTaskMemFree(v4);
      v3 = (void *)*((_QWORD *)a1 + 2);
      goto LABEL_19;
    case 6:
      v3 = (void *)*((_QWORD *)a1 + 2);
LABEL_19:
      if ( v3 )
        CoTaskMemFree(v3);
      return;
    case 7:
      v2 = (void *)*((_QWORD *)a1 + 2);
      if ( v2 )
        CoTaskMemFree(v2);
      *((_DWORD *)a1 + 2) = 0;
      break;
    case 8:
      break;
    default:
      return;
  }
  if ( a1 != (char *)-8LL )
    SysFreeString(*((BSTR *)a1 + 1));
}

```

## disassembly

```asm
0x180022790  test    rcx, rcx
0x180022793  jz      locret_180022858
0x180022799  push    rbx
0x18002279a  sub     rsp, 20h
0x18002279e  mov     edx, [rcx]
0x1800227a0  mov     rbx, rcx
0x1800227a3  sub     edx, 1
0x1800227a6  jz      loc_180022843
0x1800227ac  sub     edx, 1
0x1800227af  jz      short loc_18002282A
0x1800227b1  sub     edx, 1; unsigned int
0x1800227b4  jz      short loc_18002281F
0x1800227b6  sub     edx, 1
0x1800227b9  jz      short loc_1800227FF
0x1800227bb  sub     edx, 2
0x1800227be  jz      short loc_1800227F9
0x1800227c0  sub     edx, 1
0x1800227c3  jz      short loc_1800227CF
0x1800227c5  cmp     edx, 1
0x1800227c8  jz      short loc_1800227E5
0x1800227ca  jmp     loc_180022853
0x1800227cf  mov     rcx, [rcx+10h]; pv
0x1800227d3  test    rcx, rcx
0x1800227d6  jz      short loc_1800227DE
0x1800227d8  call    cs:__imp_CoTaskMemFree
0x1800227de  mov     dword ptr [rbx+8], 0
0x1800227e5  lea     rcx, [rbx+8]
0x1800227e9  test    rcx, rcx
0x1800227ec  jz      short loc_180022853
0x1800227ee  mov     rcx, [rcx]; bstrString
0x1800227f1  call    cs:__imp_SysFreeString
0x1800227f7  jmp     short loc_180022853
0x1800227f9  mov     rcx, [rcx+10h]
0x1800227fd  jmp     short loc_180022812
0x1800227ff  mov     rcx, [rcx+8]; pv
0x180022803  test    rcx, rcx
0x180022806  jz      short loc_18002280E
0x180022808  call    cs:__imp_CoTaskMemFree
0x18002280e  mov     rcx, [rbx+10h]; pv
0x180022812  test    rcx, rcx
0x180022815  jz      short loc_180022853
0x180022817  call    cs:__imp_CoTaskMemFree
0x18002281d  jmp     short loc_180022853
0x18002281f  add     rcx, 8; struct tagDSDeployment *
0x180022823  call    ?DsqFreeObject@@YAXPEAUtagDSDeployment@@K@Z; DsqFreeObject(tagDSDeployment *,ulong)
0x180022828  jmp     short loc_180022853
0x18002282a  mov     edx, 1; unsigned int
0x18002282f  add     rcx, 8; struct tagDSUpdateMetadata *
0x180022833  mov     r9d, edx; int
0x180022836  mov     r8d, 2FAFh; unsigned int
0x18002283c  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x180022841  jmp     short loc_180022853
0x180022843  add     rcx, 8; struct tagMatchingUpdate *
0x180022847  jz      short loc_180022853
0x180022849  mov     edx, 1; int
0x18002284e  call    ?FreeObject@@YAXAEAUtagMatchingUpdate@@H@Z; FreeObject(tagMatchingUpdate &,int)
0x180022853  add     rsp, 20h
0x180022857  pop     rbx
0x180022858  retn
```
