# tson::input_archive::process<tson::nvp<ModelInstallationStatus &>,tson::nvp<ModelName &>>(tson::nvp<ModelInstallationStatus &> &&,tson::nvp<ModelName &> &&)

- ea: `0x18001099c`
- end: `0x180010a4a`
- name: `??$process@V?$nvp@AEAW4ModelInstallationStatus@@@tson@@V?$nvp@AEAW4ModelName@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAW4ModelInstallationStatus@@@1@$$QEAV?$nvp@AEAW4ModelName@@@1@@Z`
- size: `174`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001db40`

## callees

- `0x18001099c`
- `0x18001d768`
- `0x18001d7a0`
- `0x180020778`

## pseudocode

```c
char __fastcall tson::input_archive::process<tson::nvp<enum ModelInstallationStatus &>,tson::nvp<enum ModelName &>>(
        tson::input_archive *this,
        __int64 a2,
        __int64 *a3)
{
  char v3; // r9
  int v4; // edi
  _DWORD *v7; // r14
  __int64 v8; // rdx
  int v9; // edi
  __int64 v10; // rax
  _DWORD *v11; // rsi
  char result; // al
  __int64 v13; // rdx
  int v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_BYTE *)(a2 + 8);
  v4 = 0;
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v3;
  v7 = *(_DWORD **)(a2 + 16);
  v14 = 0;
  if ( tson::input_archive::search(this) )
  {
    LOBYTE(v8) = 18;
    tson::input_archive::consume_expected_marker(this, v8, 2147944029LL);
    tson::read_buffer::consume_n(*(tson::read_buffer **)this, &v14, 4u);
    v4 = v14;
  }
  *v7 = v4;
  v9 = 0;
  v10 = *a3;
  *((_BYTE *)this + 24) = *((_BYTE *)a3 + 8);
  *((_QWORD *)this + 2) = v10;
  v11 = (_DWORD *)a3[2];
  v14 = 0;
  result = tson::input_archive::search(this);
  if ( result )
  {
    LOBYTE(v13) = 18;
    tson::input_archive::consume_expected_marker(this, v13, 2147944029LL);
    result = tson::read_buffer::consume_n(*(tson::read_buffer **)this, &v14, 4u);
    v9 = v14;
  }
  *v11 = v9;
  return result;
}

```

## disassembly

```asm
0x18001099c  push    rbx
0x18001099e  push    rsi
0x18001099f  push    rdi
0x1800109a0  push    r14
0x1800109a2  sub     rsp, 28h
0x1800109a6  mov     r9b, [rdx+8]
0x1800109aa  xor     edi, edi
0x1800109ac  mov     rax, [rdx]
0x1800109af  mov     rsi, r8
0x1800109b2  mov     [rcx+10h], rax
0x1800109b6  mov     rbx, rcx
0x1800109b9  mov     [rcx+18h], r9b
0x1800109bd  mov     r14, [rdx+10h]
0x1800109c1  mov     [rsp+48h+arg_0], edi
0x1800109c5  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x1800109ca  test    al, al
0x1800109cc  jz      short loc_1800109F3
0x1800109ce  mov     r8d, 8007065Dh
0x1800109d4  mov     dl, 12h
0x1800109d6  mov     rcx, rbx
0x1800109d9  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x1800109de  mov     rcx, [rbx]; this
0x1800109e1  lea     rdx, [rsp+48h+arg_0]; void *
0x1800109e6  lea     r8d, [rdi+4]; unsigned __int64
0x1800109ea  call    ?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z; tson::read_buffer::consume_n(void *,unsigned __int64)
0x1800109ef  mov     edi, [rsp+48h+arg_0]
0x1800109f3  mov     [r14], edi
0x1800109f6  xor     edi, edi
0x1800109f8  mov     cl, [rsi+8]
0x1800109fb  mov     rax, [rsi]
0x1800109fe  mov     [rbx+18h], cl
0x180010a01  mov     rcx, rbx; this
0x180010a04  mov     [rbx+10h], rax
0x180010a08  mov     rsi, [rsi+10h]
0x180010a0c  mov     [rsp+48h+arg_0], edi
0x180010a10  call    ?search@input_archive@tson@@AEAA_NXZ; tson::input_archive::search(void)
0x180010a15  test    al, al
0x180010a17  jz      short loc_180010A3E
0x180010a19  mov     r8d, 8007065Dh
0x180010a1f  mov     dl, 12h
0x180010a21  mov     rcx, rbx
0x180010a24  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x180010a29  mov     rcx, [rbx]; this
0x180010a2c  lea     rdx, [rsp+48h+arg_0]; void *
0x180010a31  lea     r8d, [rdi+4]; unsigned __int64
0x180010a35  call    ?consume_n@read_buffer@tson@@QEAA_NPEAX_K@Z; tson::read_buffer::consume_n(void *,unsigned __int64)
0x180010a3a  mov     edi, [rsp+48h+arg_0]
0x180010a3e  mov     [rsi], edi
0x180010a40  add     rsp, 28h
0x180010a44  pop     r14
0x180010a46  pop     rdi
0x180010a47  pop     rsi
0x180010a48  pop     rbx
0x180010a49  retn
```
