# FxStubDriverUnloadCommon(void)

- ea: `0x14000bd0c`
- end: `0x14000be1f`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `275`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000be64`
- `0x14000bfe0`

## callees

- `0x14000bd0c`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000bde6`
- `ntoskrnl!DbgPrintEx` at `0x14000bde6`
- `WDFLDR!WdfVersionUnbind` at `0x14000be07`
- `WDFLDR!WdfVersionUnbind` at `0x14000be07`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000bdc4`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000bda2`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000bdc4`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  __int64 *v0; // rcx
  __int64 *v1; // rdi
  __int64 *v2; // rbx
  void (__fastcall *v3)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), __int64 *, _LIST_ENTRY *, __int64 *); // rax

  if ( off_140013228 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
  {
    v0 = &BthCoreCx_BIND_INFO;
    if ( *(_DWORD *)off_140013228 == 120 )
      v1 = (__int64 *)((char *)off_140013228 + 120);
    else
      v1 = (__int64 *)((char *)off_140013228 + 80);
    while ( 1 )
    {
      while ( v0 + 1 <= v1 && !*v0 )
        ++v0;
      if ( v0 < v1 )
      {
        if ( (v0 + 10 > v1 || *(_DWORD *)v0 != 80) && (v0 + 15 > v1 || *(_DWORD *)v0 != 120) )
        {
LABEL_21:
          DbgPrintEx(0x4Du, 0, "FxGetNextClassBindInfo failed\n");
          break;
        }
        v2 = v0;
      }
      else
      {
        v2 = v1;
      }
      if ( !v2 )
        goto LABEL_21;
      if ( v2 >= v1 )
        break;
      v3 = (void (__fastcall *)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), __int64 *, _LIST_ENTRY *, __int64 *))v2[8];
      if ( v3 )
        v3(WdfVersionUnbindClass, &qword_1400130C0, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v2);
      else
        WdfVersionUnbindClass(&qword_1400130C0, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v2);
      v0 = (__int64 *)((char *)v2 + *(unsigned int *)v2);
    }
  }
  WdfVersionUnbind(&WPP_MAIN_CB.Queue, &qword_1400130C0, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
}

```

## disassembly

```asm
0x14000bd0c  mov     [rsp+arg_0], rbx
0x14000bd11  push    rdi
0x14000bd12  sub     rsp, 30h
0x14000bd16  mov     rdi, cs:off_140013228
0x14000bd1d  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000bd24  cmp     rdi, rax
0x14000bd27  jz      loc_14000BDF2
0x14000bd2d  cmp     dword ptr [rdi], 78h ; 'x'
0x14000bd30  lea     rcx, _BthCoreCx_BIND_INFO
0x14000bd37  jnz     short loc_14000BD3F
0x14000bd39  add     rdi, 78h ; 'x'
0x14000bd3d  jmp     short loc_14000BD4F
0x14000bd3f  add     rdi, 50h ; 'P'
0x14000bd43  jmp     short loc_14000BD4F
0x14000bd45  cmp     qword ptr [rcx], 0
0x14000bd49  jnz     short loc_14000BD58
0x14000bd4b  add     rcx, 8
0x14000bd4f  lea     rax, [rcx+8]
0x14000bd53  cmp     rax, rdi
0x14000bd56  jbe     short loc_14000BD45
0x14000bd58  cmp     rcx, rdi
0x14000bd5b  jb      short loc_14000BD62
0x14000bd5d  mov     rbx, rdi
0x14000bd60  jmp     short loc_14000BD81
0x14000bd62  lea     rax, [rcx+50h]
0x14000bd66  cmp     rax, rdi
0x14000bd69  ja      short loc_14000BD70
0x14000bd6b  cmp     dword ptr [rcx], 50h ; 'P'
0x14000bd6e  jz      short loc_14000BD7E
0x14000bd70  lea     rax, [rcx+78h]
0x14000bd74  cmp     rax, rdi
0x14000bd77  ja      short loc_14000BDDA
0x14000bd79  cmp     dword ptr [rcx], 78h ; 'x'
0x14000bd7c  jnz     short loc_14000BDDA
0x14000bd7e  mov     rbx, rcx
0x14000bd81  test    rbx, rbx
0x14000bd84  jz      short loc_14000BDDA
0x14000bd86  cmp     rbx, rdi
0x14000bd89  jnb     short loc_14000BDF2
0x14000bd8b  mov     rax, [rbx+40h]
0x14000bd8f  test    rax, rax
0x14000bd92  jz      short loc_14000BDB3
0x14000bd94  mov     r8, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000bd9b  lea     rdx, qword_1400130C0
0x14000bda2  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x14000bda9  mov     r9, rbx
0x14000bdac  call    _guard_dispatch_icall
0x14000bdb1  jmp     short loc_14000BDD0
0x14000bdb3  mov     rdx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000bdba  lea     rcx, qword_1400130C0
0x14000bdc1  mov     r8, rbx
0x14000bdc4  call    cs:__imp_WdfVersionUnbindClass
0x14000bdcb  nop     dword ptr [rax+rax+00h]
0x14000bdd0  mov     ecx, [rbx]
0x14000bdd2  add     rcx, rbx
0x14000bdd5  jmp     loc_14000BD4F
0x14000bdda  xor     edx, edx; Level
0x14000bddc  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x14000bde3  lea     ecx, [rdx+4Dh]; ComponentId
0x14000bde6  call    cs:__imp_DbgPrintEx
0x14000bded  nop     dword ptr [rax+rax+00h]
0x14000bdf2  mov     r8, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000bdf9  lea     rdx, qword_1400130C0
0x14000be00  lea     rcx, WPP_MAIN_CB.Queue
0x14000be07  call    cs:__imp_WdfVersionUnbind
0x14000be0e  nop     dword ptr [rax+rax+00h]
0x14000be13  mov     rbx, [rsp+38h+arg_0]
0x14000be18  add     rsp, 30h
0x14000be1c  pop     rdi
0x14000be1d  retn
```
