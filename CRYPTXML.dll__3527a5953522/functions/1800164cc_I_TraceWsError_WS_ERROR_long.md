# I_TraceWsError(_WS_ERROR *,long)

- ea: `0x1800164cc`
- end: `0x18001655d`
- name: `?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z`
- size: `145`
- prototype: `void __fastcall(struct _WS_ERROR *error, int)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001d00`
- `0x180002470`
- `0x180004670`
- `0x180006150`
- `0x180009f80`
- `0x18000c2d0`
- `0x18000c990`
- `0x18000d1f0`
- `0x18000e290`
- `0x18000e750`
- `0x18000fe50`
- `0x180012600`
- `0x180016820`
- `0x180016a0c`
- `0x180016c38`

## callees

- `0x180014ce0`
- `0x1800164cc`

## import_xrefs

- `webservices!WsGetErrorString` at `0x180016524`
- `webservices!WsGetErrorString` at `0x180016524`
- `webservices!WsGetErrorProperty` at `0x1800164fa`
- `webservices!WsGetErrorProperty` at `0x1800164fa`

## pseudocode

```c
void __fastcall I_TraceWsError(struct _WS_ERROR *error)
{
  ULONG i; // ebx
  WS_STRING string; // [rsp+20h] [rbp-18h] BYREF
  ULONG v4; // [rsp+48h] [rbp+10h] BYREF

  if ( error )
  {
    v4 = 0;
    if ( WsGetErrorProperty(error, WS_ERROR_PROPERTY_STRING_COUNT, &v4, 4u) >= 0 )
    {
      for ( i = 0; i < v4; ++i )
      {
        string = 0;
        if ( WsGetErrorString(error, i, &string) >= 0 )
          WPPTraceLogA("%.*S\n", string.length, string.chars);
      }
    }
  }
}

```

## disassembly

```asm
0x1800164cc  test    rcx, rcx
0x1800164cf  jz      locret_18001655B
0x1800164d5  mov     rax, rsp
0x1800164d8  mov     [rax+8], rbx
0x1800164dc  mov     [rax+10h], edx
0x1800164df  push    rdi
0x1800164e0  sub     rsp, 30h
0x1800164e4  mov     r9d, 4; bufferSize
0x1800164ea  mov     dword ptr [rax+10h], 0
0x1800164f1  lea     r8, [rax+10h]; buffer
0x1800164f5  xor     edx, edx; id
0x1800164f7  mov     rdi, rcx
0x1800164fa  call    cs:__imp_WsGetErrorProperty
0x180016501  nop     dword ptr [rax+rax+00h]
0x180016506  test    eax, eax
0x180016508  js      short loc_180016551
0x18001650a  xor     ebx, ebx
0x18001650c  cmp     [rsp+38h+arg_8], ebx
0x180016510  jbe     short loc_180016551
0x180016512  xorps   xmm0, xmm0
0x180016515  lea     r8, [rsp+38h+string]; string
0x18001651a  mov     edx, ebx; index
0x18001651c  mov     rcx, rdi; error
0x18001651f  movups  xmmword ptr [rsp+38h+string.length], xmm0
0x180016524  call    cs:__imp_WsGetErrorString
0x18001652b  nop     dword ptr [rax+rax+00h]
0x180016530  test    eax, eax
0x180016532  js      short loc_180016549
0x180016534  mov     r8, [rsp+38h+string.chars]
0x180016539  lea     rcx, aS; "%.*S\n"
0x180016540  mov     edx, [rsp+38h+string.length]
0x180016544  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180016549  inc     ebx
0x18001654b  cmp     ebx, [rsp+38h+arg_8]
0x18001654f  jb      short loc_180016512
0x180016551  mov     rbx, [rsp+38h+arg_0]
0x180016556  add     rsp, 30h
0x18001655a  pop     rdi
0x18001655b  retn
```
