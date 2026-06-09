# CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *)

- ea: `0x180003990`
- end: `0x180003b7c`
- name: `??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0@Z`
- size: `492`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180006304`

## callees

- `0x180003990`
- `0x180007018`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a4b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a82`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003ab9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003af0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003b20`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003b50`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a4b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003a82`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003ab9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003af0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003b20`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180003b50`

## string_xrefs

- `0x1800039a0`: `TraceServiceStatus`

## pseudocode

```c
_QWORD *__fastcall CTraceFuncW<long>::CTraceFuncW<long>(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  const char *v12; // rbx
  char *v13; // rax
  __int64 v14; // rcx
  __int64 *v15; // rdx
  char *v16; // rax
  char *v17; // rax
  char *v18; // rax
  char *v19; // rax
  char *v20; // rax
  char *v21; // rax

  v4 = dword_1800134CC;
  *a1 = "TraceServiceStatus";
  a1[1] = a4;
  a1[2] = 0;
  a1[3] = 0;
  v6 = v4 - 4;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 && (byte_1800134CB & 0x10) != 0 )
              {
                v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
                v13 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
                if ( v13 )
                  v12 = v13 + 1;
                v15 = Extension_TraceFunction_Enter;
LABEL_36:
                McTemplateU0ssqz_EventWriteTransfer(v14, v15, v12);
              }
            }
            else if ( (byte_1800134CA & 0x10) != 0 )
            {
              v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
              v16 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
              if ( v16 )
                v12 = v16 + 1;
              v15 = TokenProvider_TraceFunction_Enter;
              goto LABEL_36;
            }
          }
          else if ( (byte_1800134C9 & 0x10) != 0 )
          {
            v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
            v17 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
            if ( v17 )
              v12 = v17 + 1;
            v15 = WlidBho_TraceFunction_Enter;
            goto LABEL_36;
          }
        }
        else if ( (byte_1800134C8 & 8) != 0 )
        {
          v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
          v18 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
          if ( v18 )
            v12 = v18 + 1;
          v15 = WlidProv_TraceFunction_Enter;
          goto LABEL_36;
        }
      }
      else if ( (byte_1800134C7 & 8) != 0 )
      {
        v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
        v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
        if ( v19 )
          v12 = v19 + 1;
        v15 = WlidCli_TraceFunction_Enter;
        goto LABEL_36;
      }
    }
    else if ( byte_1800134C5 < 0 )
    {
      v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
      v20 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
      if ( v20 )
        v12 = v20 + 1;
      v15 = WlidModern_TraceFunction_Enter;
      goto LABEL_36;
    }
  }
  else if ( (byte_1800134C4 & 4) != 0 )
  {
    v12 = "onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp";
    v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp", 92);
    if ( v21 )
      v12 = v21 + 1;
    v15 = WlidSvc_TraceFunction_Enter;
    goto LABEL_36;
  }
  return a1;
}

```

## disassembly

```asm
0x180003990  mov     [rsp+arg_0], rbx
0x180003995  push    rdi
0x180003996  sub     rsp, 30h
0x18000399a  mov     edx, cs:dword_1800134CC
0x1800039a0  lea     rax, aTraceservicest; "TraceServiceStatus"
0x1800039a7  mov     [rcx], rax
0x1800039aa  mov     rdi, rcx
0x1800039ad  mov     [rcx+8], r9
0x1800039b1  mov     qword ptr [rcx+10h], 0
0x1800039b9  mov     qword ptr [rcx+18h], 0
0x1800039c1  sub     edx, 4
0x1800039c4  jz      loc_180003B38
0x1800039ca  sub     edx, 1
0x1800039cd  jz      loc_180003B08
0x1800039d3  sub     edx, 1
0x1800039d6  jz      loc_180003AD4
0x1800039dc  sub     edx, 1
0x1800039df  jz      loc_180003A9D
0x1800039e5  sub     edx, 1
0x1800039e8  jz      short loc_180003A66
0x1800039ea  sub     edx, 1
0x1800039ed  jz      short loc_180003A2F
0x1800039ef  cmp     edx, 1
0x1800039f2  jnz     loc_180003B6E
0x1800039f8  test    cs:byte_1800134CB, 10h
0x1800039ff  jz      loc_180003B6E
0x180003a05  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003a0c  mov     edx, 5Ch ; '\'; Ch
0x180003a11  mov     rcx, rbx; Str
0x180003a14  call    cs:__imp_strrchr
0x180003a1a  test    rax, rax
0x180003a1d  jz      short loc_180003A23
0x180003a1f  lea     rbx, [rax+1]
0x180003a23  lea     rdx, Extension_TraceFunction_Enter
0x180003a2a  jmp     loc_180003B66
0x180003a2f  test    cs:byte_1800134CA, 10h
0x180003a36  jz      loc_180003B6E
0x180003a3c  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003a43  mov     edx, 5Ch ; '\'; Ch
0x180003a48  mov     rcx, rbx; Str
0x180003a4b  call    cs:__imp_strrchr
0x180003a51  test    rax, rax
0x180003a54  jz      short loc_180003A5A
0x180003a56  lea     rbx, [rax+1]
0x180003a5a  lea     rdx, TokenProvider_TraceFunction_Enter
0x180003a61  jmp     loc_180003B66
0x180003a66  test    cs:byte_1800134C9, 10h
0x180003a6d  jz      loc_180003B6E
0x180003a73  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003a7a  mov     edx, 5Ch ; '\'; Ch
0x180003a7f  mov     rcx, rbx; Str
0x180003a82  call    cs:__imp_strrchr
0x180003a88  test    rax, rax
0x180003a8b  jz      short loc_180003A91
0x180003a8d  lea     rbx, [rax+1]
0x180003a91  lea     rdx, WlidBho_TraceFunction_Enter
0x180003a98  jmp     loc_180003B66
0x180003a9d  test    cs:byte_1800134C8, 8
0x180003aa4  jz      loc_180003B6E
0x180003aaa  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003ab1  mov     edx, 5Ch ; '\'; Ch
0x180003ab6  mov     rcx, rbx; Str
0x180003ab9  call    cs:__imp_strrchr
0x180003abf  test    rax, rax
0x180003ac2  jz      short loc_180003AC8
0x180003ac4  lea     rbx, [rax+1]
0x180003ac8  lea     rdx, WlidProv_TraceFunction_Enter
0x180003acf  jmp     loc_180003B66
0x180003ad4  test    cs:byte_1800134C7, 8
0x180003adb  jz      loc_180003B6E
0x180003ae1  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003ae8  mov     edx, 5Ch ; '\'; Ch
0x180003aed  mov     rcx, rbx; Str
0x180003af0  call    cs:__imp_strrchr
0x180003af6  test    rax, rax
0x180003af9  jz      short loc_180003AFF
0x180003afb  lea     rbx, [rax+1]
0x180003aff  lea     rdx, WlidCli_TraceFunction_Enter
0x180003b06  jmp     short loc_180003B66
0x180003b08  cmp     cs:byte_1800134C5, 0
0x180003b0f  jge     short loc_180003B6E
0x180003b11  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003b18  mov     edx, 5Ch ; '\'; Ch
0x180003b1d  mov     rcx, rbx; Str
0x180003b20  call    cs:__imp_strrchr
0x180003b26  test    rax, rax
0x180003b29  jz      short loc_180003B2F
0x180003b2b  lea     rbx, [rax+1]
0x180003b2f  lea     rdx, WlidModern_TraceFunction_Enter
0x180003b36  jmp     short loc_180003B66
0x180003b38  test    cs:byte_1800134C4, 4
0x180003b3f  jz      short loc_180003B6E
0x180003b41  lea     rbx, Str; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003b48  mov     edx, 5Ch ; '\'; Ch
0x180003b4d  mov     rcx, rbx; Str
0x180003b50  call    cs:__imp_strrchr
0x180003b56  test    rax, rax
0x180003b59  jz      short loc_180003B5F
0x180003b5b  lea     rbx, [rax+1]
0x180003b5f  lea     rdx, WlidSvc_TraceFunction_Enter
0x180003b66  mov     r8, rbx
0x180003b69  call    McTemplateU0ssqz_EventWriteTransfer
0x180003b6e  mov     rbx, [rsp+38h+arg_0]
0x180003b73  mov     rax, rdi
0x180003b76  add     rsp, 30h
0x180003b7a  pop     rdi
0x180003b7b  retn
```
