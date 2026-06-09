# UpdateIndex(_INDEX_STRUCT *)

- ea: `0x18000bbb8`
- end: `0x18000bc72`
- name: `?UpdateIndex@@YAKPEAU_INDEX_STRUCT@@@Z`
- size: `186`
- prototype: `unsigned int __fastcall(struct _INDEX_STRUCT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800064a8`

## callees

- `0x180004dec`
- `0x18000b3fc`
- `0x18000bbb8`
- `0x18000d728`
- `0x1800135cc`

## pseudocode

```c
__int64 __fastcall UpdateIndex(struct _INDEX_STRUCT *a1)
{
  unsigned int v2; // edi
  struct UNNAMED_STRUCT_SCANNER *v3; // rcx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = ScanSystem(a1);
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 12;
      goto LABEL_13;
    }
  }
  else
  {
    v3 = (struct UNNAMED_STRUCT_SCANNER *)*((_QWORD *)a1 + 3);
    v7 = (unsigned __int64)a1;
    v2 = ScannerScanDownloads(v3, &v7);
    if ( v2 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 11;
LABEL_13:
        WPP_SF_d(v4[2], v5, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v2);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000bbb8  mov     [rsp+arg_0], rbx
0x18000bbbd  push    rdi
0x18000bbbe  sub     rsp, 30h
0x18000bbc2  xorps   xmm0, xmm0
0x18000bbc5  mov     rbx, rcx
0x18000bbc8  movups  [rsp+38h+var_18], xmm0
0x18000bbcd  test    rcx, rcx
0x18000bbd0  jnz     short loc_18000BBD7
0x18000bbd2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bbd7  cmp     dword ptr [rbx], 494E4445h
0x18000bbdd  jz      short loc_18000BBE4
0x18000bbdf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000bbe4  mov     rcx, rbx; struct _INDEX_STRUCT *
0x18000bbe7  call    ScanSystem
0x18000bbec  mov     edi, eax
0x18000bbee  test    eax, eax
0x18000bbf0  jnz     short loc_18000BC34
0x18000bbf2  mov     rcx, [rbx+18h]; struct UNNAMED_STRUCT_SCANNER *
0x18000bbf6  lea     rdx, [rsp+38h+var_18]; void *
0x18000bbfb  mov     qword ptr [rsp+38h+var_18], rbx
0x18000bc00  mov     qword ptr [rsp+38h+var_18+8], 0
0x18000bc09  call    ?ScannerScanDownloads@@YAKPEAUUNNAMED_STRUCT_SCANNER@@PEAX@Z; ScannerScanDownloads(UNNAMED_STRUCT_SCANNER *,void *)
0x18000bc0e  mov     edi, eax
0x18000bc10  test    eax, eax
0x18000bc12  jz      short loc_18000BC65
0x18000bc14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc1b  lea     rax, WPP_GLOBAL_Control
0x18000bc22  cmp     rcx, rax
0x18000bc25  jz      short loc_18000BC65
0x18000bc27  test    byte ptr [rcx+1Ch], 1
0x18000bc2b  jz      short loc_18000BC65
0x18000bc2d  mov     edx, 0Bh
0x18000bc32  jmp     short loc_18000BC52
0x18000bc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc3b  lea     rax, WPP_GLOBAL_Control
0x18000bc42  cmp     rcx, rax
0x18000bc45  jz      short loc_18000BC65
0x18000bc47  test    byte ptr [rcx+1Ch], 1
0x18000bc4b  jz      short loc_18000BC65
0x18000bc4d  mov     edx, 0Ch
0x18000bc52  mov     rcx, [rcx+10h]
0x18000bc56  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000bc5d  mov     r9d, edi
0x18000bc60  call    WPP_SF_d
0x18000bc65  mov     rbx, [rsp+38h+arg_0]
0x18000bc6a  mov     eax, edi
0x18000bc6c  add     rsp, 30h
0x18000bc70  pop     rdi
0x18000bc71  retn
```
