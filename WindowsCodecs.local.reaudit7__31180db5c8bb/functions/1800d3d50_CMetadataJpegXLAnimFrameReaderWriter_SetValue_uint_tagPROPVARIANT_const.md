# CMetadataJpegXLAnimFrameReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1800d3d50`
- end: `0x1800d3e5a`
- name: `?SetValue@CMetadataJpegXLAnimFrameReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(LPVOID *this, int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800bd9d4`
- `0x1800d3d50`
- `0x1800d3f1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3d8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3df0`

## pseudocode

```c
__int64 __fastcall CMetadataJpegXLAnimFrameReaderWriter::SetValue(
        LPVOID *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  _QWORD *v7; // r14
  LARGE_INTEGER hVal; // r8
  __int64 v9; // rsi
  __int64 v10; // r9
  int v11; // eax
  int v12; // ecx
  int v13; // esi

  v5 = 0;
  v6 = a2 - 1;
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      if ( a3->vt == 31 )
      {
        v7 = this + 22;
        CoTaskMemFree(this[22]);
        *v7 = 0;
        hVal = a3->hVal;
        v9 = -1;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(hVal.QuadPart + 2 * v10) );
        v11 = _AllocStringWorker<CTCoAllocPolicy>();
        v5 = v11;
        if ( v11 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            return v5;
          v12 = v11;
          goto LABEL_21;
        }
        do
          ++v9;
        while ( *(_WORD *)(*v7 + 2 * v9) );
        v13 = 2 * v9 + 2;
        goto LABEL_14;
      }
      if ( !a3->vt )
      {
        CoTaskMemFree(this[22]);
        this[22] = 0;
        v13 = 0;
LABEL_14:
        *((_DWORD *)this + 41) = v13;
        return v5;
      }
    }
  }
  else
  {
    if ( a3->vt == 19 )
    {
      *((_DWORD *)this + 39) = a3->lVal;
      *((_BYTE *)this + 168) = 1;
      return v5;
    }
    if ( !a3->vt )
    {
      *((_BYTE *)this + 168) = 0;
      return v5;
    }
  }
  v5 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
  {
    v12 = -2147024809;
LABEL_21:
    DoStackCapture(v12);
  }
  return v5;
}

```

## disassembly

```asm
0x1800d3d50  push    rbx
0x1800d3d52  push    rbp
0x1800d3d53  push    rsi
0x1800d3d54  push    rdi
0x1800d3d55  push    r14
0x1800d3d57  sub     rsp, 30h
0x1800d3d5b  xor     ebp, ebp
0x1800d3d5d  mov     rsi, r8
0x1800d3d60  mov     rdi, rcx
0x1800d3d63  mov     ebx, ebp
0x1800d3d65  sub     edx, 1
0x1800d3d68  jz      loc_1800D3E0F
0x1800d3d6e  cmp     edx, 1
0x1800d3d71  jnz     loc_1800D3E38
0x1800d3d77  movzx   eax, word ptr [r8]
0x1800d3d7b  cmp     ax, 1Fh
0x1800d3d7f  jnz     short loc_1800D3DE4
0x1800d3d81  lea     r14, [rcx+0B0h]
0x1800d3d88  mov     rcx, [r14]; pv
0x1800d3d8b  call    cs:__imp_CoTaskMemFree
0x1800d3d92  nop     dword ptr [rax+rax+00h]
0x1800d3d97  mov     [r14], rbp
0x1800d3d9a  mov     r8, [rsi+8]
0x1800d3d9e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d3da2  mov     r9, rsi
0x1800d3da5  inc     r9
0x1800d3da8  cmp     [r8+r9*2], bp
0x1800d3dad  jnz     short loc_1800D3DA5
0x1800d3daf  mov     [rsp+58h+var_30], r14
0x1800d3db4  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800d3db9  mov     ebx, eax
0x1800d3dbb  test    eax, eax
0x1800d3dbd  jns     short loc_1800D3DCF
0x1800d3dbf  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800d3dc5  jz      short loc_1800D3DCB
0x1800d3dc7  mov     ecx, eax
0x1800d3dc9  jmp     short loc_1800D3E47
0x1800d3dcb  test    eax, eax
0x1800d3dcd  js      short loc_1800D3E4C
0x1800d3dcf  mov     rax, [r14]
0x1800d3dd2  inc     rsi
0x1800d3dd5  cmp     [rax+rsi*2], bp
0x1800d3dd9  jnz     short loc_1800D3DD2
0x1800d3ddb  lea     esi, ds:2[rsi*2]
0x1800d3de2  jmp     short loc_1800D3E05
0x1800d3de4  test    ax, ax
0x1800d3de7  jnz     short loc_1800D3E38
0x1800d3de9  mov     rcx, [rcx+0B0h]; pv
0x1800d3df0  call    cs:__imp_CoTaskMemFree
0x1800d3df7  nop     dword ptr [rax+rax+00h]
0x1800d3dfc  mov     [rdi+0B0h], rbp
0x1800d3e03  mov     esi, ebp
0x1800d3e05  mov     eax, 0A4h
0x1800d3e0a  mov     [rax+rdi], esi
0x1800d3e0d  jmp     short loc_1800D3E4C
0x1800d3e0f  cmp     word ptr [r8], 13h
0x1800d3e14  jnz     short loc_1800D3E29
0x1800d3e16  mov     eax, [r8+8]
0x1800d3e1a  mov     [rcx+9Ch], eax
0x1800d3e20  mov     byte ptr [rcx+0A8h], 1
0x1800d3e27  jmp     short loc_1800D3E4C
0x1800d3e29  cmp     [r8], bp
0x1800d3e2d  jnz     short loc_1800D3E38
0x1800d3e2f  mov     [rcx+0A8h], bpl
0x1800d3e36  jmp     short loc_1800D3E4C
0x1800d3e38  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800d3e3e  mov     ebx, 80070057h
0x1800d3e43  jz      short loc_1800D3E4C
0x1800d3e45  mov     ecx, ebx; int
0x1800d3e47  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3e4c  mov     eax, ebx
0x1800d3e4e  add     rsp, 30h
0x1800d3e52  pop     r14
0x1800d3e54  pop     rdi
0x1800d3e55  pop     rsi
0x1800d3e56  pop     rbp
0x1800d3e57  pop     rbx
0x1800d3e58  retn
```
