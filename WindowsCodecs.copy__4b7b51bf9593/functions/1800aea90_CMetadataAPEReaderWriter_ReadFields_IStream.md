# CMetadataAPEReaderWriter::ReadFields(IStream *)

- ea: `0x1800aea90`
- end: `0x1800aec60`
- name: `?ReadFields@CMetadataAPEReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CMetadataAPEReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180036cb4`
- `0x1800aea90`
- `0x1800bb784`
- `0x1800c5240`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aeb44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aeb44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aec26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aec26`

## pseudocode

```c
__int64 __fastcall CMetadataAPEReaderWriter::ReadFields(CMetadataAPEReaderWriter *this, struct IStream *a2)
{
  int FullBufferFromStream; // eax
  unsigned int v5; // ebx
  bool v6; // cf
  int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // esi
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rbp
  int v12; // eax
  bool v14; // zf
  int v15; // ecx
  int v16[10]; // [rsp+20h] [rbp-28h] BYREF
  char v17; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int8 v18; // [rsp+68h] [rbp+20h] BYREF
  char v19; // [rsp+69h] [rbp+21h]
  unsigned __int8 v20; // [rsp+6Ah] [rbp+22h]

  v17 = 0;
  FullBufferFromStream = ReadFullBufferFromStream(a2, &v18, 3u);
  v5 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_21;
  v6 = v18 < 0x21u;
  if ( v18 == 33 && (v6 = v19 != -1, v19 == -1) && (v6 = v20 < 0xBu, v20 == 11) )
    v7 = 0;
  else
    v7 = v6 ? -1 : 1;
  if ( v7 )
  {
    v5 = -2003292317;
    goto LABEL_18;
  }
  FullBufferFromStream = ReadFullBufferFromStream(a2, (char *)this + 152, 0xBu);
  v5 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
LABEL_21:
    if ( !(_DWORD)g_doStackCaptures )
      return v5;
    v15 = FullBufferFromStream;
LABEL_23:
    DoStackCapture(v15);
    return v5;
  }
  v8 = *((_DWORD *)this + 32) - *((_DWORD *)this + 34);
  *((_DWORD *)this + 41) = 1;
  if ( v8 < 0xF )
  {
    v5 = -2147024362;
LABEL_18:
    v14 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_19;
  }
  v9 = v8 - 15;
  v10 = (unsigned __int8 *)CoTaskMemAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    goto LABEL_18;
  }
  v12 = ReadFullBufferFromStream(a2, v10, v9);
  v5 = v12;
  if ( v12 >= 0 )
  {
    v16[0] = 0;
    v12 = CMetadataAPEReaderWriter::HrCheckApplicationData(this, v11, v9, v16);
    v5 = v12;
    if ( v12 >= 0 )
    {
      if ( v16[0] == 1 )
        --v9;
      *((_WORD *)this + 84) = 4113;
      *((_DWORD *)this + 44) = v9;
      *((_QWORD *)this + 23) = v11;
      v5 = ReadFullBufferFromStream(a2, &v17, 1u);
      if ( (v5 & 0x80000000) != 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v5;
LABEL_20:
        v15 = v5;
        goto LABEL_23;
      }
      if ( !v17 )
        return v5;
      v5 = -2003292317;
      v14 = (_DWORD)g_doStackCaptures == 0;
LABEL_19:
      if ( v14 )
        return v5;
      goto LABEL_20;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v12);
  CoTaskMemFree(v11);
  return v5;
}

```

## disassembly

```asm
0x1800aea90  mov     rax, rsp
0x1800aea93  mov     [rax+8], rbx
0x1800aea97  mov     [rax+10h], rbp
0x1800aea9b  push    rsi
0x1800aea9c  push    rdi
0x1800aea9d  push    r14
0x1800aea9f  sub     rsp, 30h
0x1800aeaa3  mov     r14, rdx
0x1800aeaa6  mov     byte ptr [rax+18h], 0
0x1800aeaaa  mov     rdi, rcx
0x1800aeaad  lea     rdx, [rax+20h]; void *
0x1800aeab1  mov     rcx, r14; struct IStream *
0x1800aeab4  mov     r8d, 3; unsigned int
0x1800aeaba  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800aeabf  mov     ebx, eax
0x1800aeac1  test    eax, eax
0x1800aeac3  js      loc_1800AEC01
0x1800aeac9  mov     al, [rsp+48h+arg_18]
0x1800aeacd  cmp     al, cs:byte_1801F7A70
0x1800aead3  jnz     loc_1800AEC38
0x1800aead9  mov     al, [rsp+48h+arg_19]
0x1800aeadd  cmp     al, cs:byte_1801F7A71
0x1800aeae3  jnz     loc_1800AEC38
0x1800aeae9  mov     al, [rsp+48h+arg_1A]
0x1800aeaed  cmp     al, cs:byte_1801F7A72
0x1800aeaf3  jnz     loc_1800AEC38
0x1800aeaf9  xor     eax, eax
0x1800aeafb  test    eax, eax
0x1800aeafd  jnz     loc_1800AEC42
0x1800aeb03  lea     rdx, [rdi+98h]; void *
0x1800aeb0a  mov     rcx, r14; struct IStream *
0x1800aeb0d  lea     r8d, [rax+0Bh]; unsigned int
0x1800aeb11  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800aeb16  mov     ebx, eax
0x1800aeb18  test    eax, eax
0x1800aeb1a  js      loc_1800AEC01
0x1800aeb20  mov     esi, [rdi+80h]
0x1800aeb26  sub     esi, [rdi+88h]
0x1800aeb2c  mov     dword ptr [rdi+0A4h], 1
0x1800aeb36  cmp     esi, 0Fh
0x1800aeb39  jb      loc_1800AEBEF
0x1800aeb3f  add     esi, 0FFFFFFF1h
0x1800aeb42  mov     ecx, esi; cb
0x1800aeb44  call    cs:__imp_CoTaskMemAlloc
0x1800aeb4a  mov     rbp, rax
0x1800aeb4d  test    rax, rax
0x1800aeb50  jz      loc_1800AEC49
0x1800aeb56  mov     r8d, esi; unsigned int
0x1800aeb59  mov     rdx, rax; void *
0x1800aeb5c  mov     rcx, r14; struct IStream *
0x1800aeb5f  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800aeb64  mov     ebx, eax
0x1800aeb66  test    eax, eax
0x1800aeb68  js      loc_1800AEC13
0x1800aeb6e  lea     r9, [rsp+48h+var_28]; int *
0x1800aeb73  mov     [rsp+48h+var_28], 0
0x1800aeb7b  mov     r8d, esi; unsigned int
0x1800aeb7e  mov     rdx, rbp; unsigned __int8 *
0x1800aeb81  mov     rcx, rdi; this
0x1800aeb84  call    ?HrCheckApplicationData@CMetadataAPEReaderWriter@@MEAAJPEAEIPEAH@Z; CMetadataAPEReaderWriter::HrCheckApplicationData(uchar *,uint,int *)
0x1800aeb89  mov     ebx, eax
0x1800aeb8b  test    eax, eax
0x1800aeb8d  js      loc_1800AEC13
0x1800aeb93  cmp     [rsp+48h+var_28], 1
0x1800aeb98  jz      loc_1800AEC50
0x1800aeb9e  mov     r8d, 1; unsigned int
0x1800aeba4  mov     word ptr [rdi+0A8h], 1011h
0x1800aebad  lea     rdx, [rsp+48h+arg_10]; void *
0x1800aebb2  mov     [rdi+0B0h], esi
0x1800aebb8  mov     rcx, r14; struct IStream *
0x1800aebbb  mov     [rdi+0B8h], rbp
0x1800aebc2  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800aebc7  mov     ebx, eax
0x1800aebc9  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800aebcf  test    ebx, ebx
0x1800aebd1  js      short loc_1800AEC2E
0x1800aebd3  cmp     [rsp+48h+arg_10], 0
0x1800aebd8  jnz     short loc_1800AEC57
0x1800aebda  mov     rbp, [rsp+48h+arg_8]
0x1800aebdf  mov     eax, ebx
0x1800aebe1  mov     rbx, [rsp+48h+arg_0]
0x1800aebe6  add     rsp, 30h
0x1800aebea  pop     r14
0x1800aebec  pop     rdi
0x1800aebed  pop     rsi
0x1800aebee  retn
0x1800aebef  mov     ebx, 80070216h
0x1800aebf4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800aebfb  jz      short loc_1800AEBDA
0x1800aebfd  mov     ecx, ebx
0x1800aebff  jmp     short loc_1800AEC0C
0x1800aec01  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800aec08  jz      short loc_1800AEBDA
0x1800aec0a  mov     ecx, eax; int
0x1800aec0c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aec11  jmp     short loc_1800AEBDA
0x1800aec13  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800aec1a  jz      short loc_1800AEC23
0x1800aec1c  mov     ecx, eax; int
0x1800aec1e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800aec23  mov     rcx, rbp; pv
0x1800aec26  call    cs:__imp_CoTaskMemFree
0x1800aec2c  jmp     short loc_1800AEBDA
0x1800aec2e  test    eax, eax
0x1800aec30  jnz     short loc_1800AEBFD
0x1800aec32  test    ebx, ebx
0x1800aec34  jns     short loc_1800AEBD3
0x1800aec36  jmp     short loc_1800AEBDA
0x1800aec38  sbb     eax, eax
0x1800aec3a  or      eax, 1
0x1800aec3d  jmp     loc_1800AEAFB
0x1800aec42  mov     ebx, 88982F63h
0x1800aec47  jmp     short loc_1800AEBF4
0x1800aec49  mov     ebx, 8007000Eh
0x1800aec4e  jmp     short loc_1800AEBF4
0x1800aec50  dec     esi
0x1800aec52  jmp     loc_1800AEB9E
0x1800aec57  mov     ebx, 88982F63h
0x1800aec5c  test    eax, eax
0x1800aec5e  jmp     short loc_1800AEBFB
```
