# _tip_PerformanceTraceHandlerTIP::evaluate(void)

- ea: `0x18000d284`
- end: `0x18000d5e5`
- name: `?evaluate@_tip_PerformanceTraceHandlerTIP@@QEAAXXZ`
- size: `865`
- prototype: `void __fastcall(_tip_PerformanceTraceHandlerTIP *this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d270`

## callees

- `0x18000d284`
- `0x18000dc8c`

## string_xrefs

- `0x18000d2d4`: `reason::get_traces_path_failed`
- `0x18000d376`: `reason::get_temp_path_failed`
- `0x18000d3e6`: `reason::get_output_path_failed`
- `0x18000d456`: `reason::move_to_output_folder_failed`
- `0x18000d48e`: `reason::get_zip_path_failed`
- `0x18000d4c6`: `reason::get_file_token_failed`
- `0x18000d4fe`: `reason::completion_toast_failed`

## pseudocode

```c
void __fastcall _tip_PerformanceTraceHandlerTIP::evaluate(_tip_PerformanceTraceHandlerTIP *this, const char *a2)
{
  const char *v2; // rax
  __int16 v3; // r9
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  char v7; // r9
  __int64 v8; // r8
  char v9; // r9
  __int64 v10; // r8
  char v11; // r9
  __int64 v12; // r8
  char v13; // r9
  __int64 v14; // r8
  char v15; // r9
  __int64 v16; // r8
  char v17; // r9
  __int64 v18; // r8
  char v19; // r9
  __int64 v20; // r8
  char v21; // r9
  __int64 v22; // r8
  char v23; // r9
  __int64 v24; // r8
  char v25; // r9
  __int64 v26; // r8
  char v27; // r9
  __int64 v28; // r8
  char v29; // r9
  __int64 v30; // r8
  char v31; // r9
  __int64 v32; // rax
  char v33; // cl

  if ( !*((_BYTE *)this + 16) )
  {
    v2 = tip2::details::reason_string((tip2::details *)"reason::scenario_inactive", a2);
    v5 = *(_QWORD *)(v4 + 8);
    if ( *(_BYTE *)(v5 + 152) != (_BYTE)v3 )
      return;
    *(_BYTE *)(v5 + 152) = v3 + 3;
    *(_WORD *)(v5 + 154) = v3 + 3;
    goto LABEL_4;
  }
  if ( *((_BYTE *)this + 17) )
  {
    if ( *((_BYTE *)this + 18) )
    {
      if ( *((_BYTE *)this + 19) )
      {
        if ( *((_BYTE *)this + 20) )
        {
          if ( *((_BYTE *)this + 21) )
          {
            if ( *((_BYTE *)this + 22) )
            {
              if ( *((_BYTE *)this + 23) )
              {
                if ( *((_BYTE *)this + 24) )
                {
                  if ( *((_BYTE *)this + 25) )
                  {
                    if ( *((_BYTE *)this + 26) )
                    {
                      if ( *((_BYTE *)this + 27) )
                      {
                        if ( *((_BYTE *)this + 28) )
                        {
                          if ( *((_BYTE *)this + 29) )
                          {
                            v32 = *((_QWORD *)this + 1);
                            v33 = *(_BYTE *)(v32 + 152);
                            if ( (*(_DWORD *)(v32 + 56) & 0x200) != 0 )
                            {
                              if ( v33 )
                                return;
                              *(_BYTE *)(v32 + 152) = 1;
                              *(_WORD *)(v32 + 154) = 0x8000;
                            }
                            else
                            {
                              if ( v33 )
                                return;
                              *(_BYTE *)(v32 + 152) = 3;
                              *(_WORD *)(v32 + 154) = 16385;
                            }
                            *(_QWORD *)(v32 + 160) = 0;
                          }
                          else
                          {
                            v2 = tip2::details::reason_string((tip2::details *)"reason::error_toast_failed", a2);
                            v5 = *(_QWORD *)(v30 + 8);
                            if ( *(_BYTE *)(v5 + 152) == v31 )
                            {
                              *(_BYTE *)(v5 + 152) = 3;
                              *(_WORD *)(v5 + 154) = 16;
                              goto LABEL_4;
                            }
                          }
                        }
                        else
                        {
                          v2 = tip2::details::reason_string((tip2::details *)"reason::starting_toast_failed", a2);
                          v5 = *(_QWORD *)(v28 + 8);
                          if ( *(_BYTE *)(v5 + 152) == v29 )
                          {
                            *(_BYTE *)(v5 + 152) = 3;
                            *(_WORD *)(v5 + 154) = 15;
                            goto LABEL_4;
                          }
                        }
                      }
                      else
                      {
                        v2 = tip2::details::reason_string((tip2::details *)"reason::completion_toast_failed", a2);
                        v5 = *(_QWORD *)(v26 + 8);
                        if ( *(_BYTE *)(v5 + 152) == v27 )
                        {
                          *(_BYTE *)(v5 + 152) = 3;
                          *(_WORD *)(v5 + 154) = 14;
                          goto LABEL_4;
                        }
                      }
                    }
                    else
                    {
                      v2 = tip2::details::reason_string((tip2::details *)"reason::get_file_token_failed", a2);
                      v5 = *(_QWORD *)(v24 + 8);
                      if ( *(_BYTE *)(v5 + 152) == v25 )
                      {
                        *(_BYTE *)(v5 + 152) = 3;
                        *(_WORD *)(v5 + 154) = 13;
                        goto LABEL_4;
                      }
                    }
                  }
                  else
                  {
                    v2 = tip2::details::reason_string((tip2::details *)"reason::get_zip_path_failed", a2);
                    v5 = *(_QWORD *)(v22 + 8);
                    if ( *(_BYTE *)(v5 + 152) == v23 )
                    {
                      *(_BYTE *)(v5 + 152) = 3;
                      *(_WORD *)(v5 + 154) = 12;
                      goto LABEL_4;
                    }
                  }
                }
                else
                {
                  v2 = tip2::details::reason_string((tip2::details *)"reason::move_to_output_folder_failed", a2);
                  v5 = *(_QWORD *)(v20 + 8);
                  if ( *(_BYTE *)(v5 + 152) == v21 )
                  {
                    *(_BYTE *)(v5 + 152) = 3;
                    *(_WORD *)(v5 + 154) = 11;
                    goto LABEL_4;
                  }
                }
              }
              else
              {
                v2 = tip2::details::reason_string((tip2::details *)"reason::ensure_output_folder_failed", a2);
                v5 = *(_QWORD *)(v18 + 8);
                if ( *(_BYTE *)(v5 + 152) == v19 )
                {
                  *(_BYTE *)(v5 + 152) = 3;
                  *(_WORD *)(v5 + 154) = 10;
                  goto LABEL_4;
                }
              }
            }
            else
            {
              v2 = tip2::details::reason_string((tip2::details *)"reason::get_output_path_failed", a2);
              v5 = *(_QWORD *)(v16 + 8);
              if ( *(_BYTE *)(v5 + 152) == v17 )
              {
                *(_BYTE *)(v5 + 152) = 3;
                *(_WORD *)(v5 + 154) = 9;
                goto LABEL_4;
              }
            }
          }
          else
          {
            v2 = tip2::details::reason_string((tip2::details *)"reason::stop_trace_failed", a2);
            v5 = *(_QWORD *)(v14 + 8);
            if ( *(_BYTE *)(v5 + 152) == v15 )
            {
              *(_BYTE *)(v5 + 152) = 3;
              *(_WORD *)(v5 + 154) = 8;
              goto LABEL_4;
            }
          }
        }
        else
        {
          v2 = tip2::details::reason_string((tip2::details *)"reason::get_temp_path_failed", a2);
          v5 = *(_QWORD *)(v12 + 8);
          if ( *(_BYTE *)(v5 + 152) == v13 )
          {
            *(_BYTE *)(v5 + 152) = 3;
            *(_WORD *)(v5 + 154) = 7;
            goto LABEL_4;
          }
        }
      }
      else
      {
        v2 = tip2::details::reason_string((tip2::details *)"reason::ensure_traces_folder_failed", a2);
        v5 = *(_QWORD *)(v10 + 8);
        if ( *(_BYTE *)(v5 + 152) == v11 )
        {
          *(_BYTE *)(v5 + 152) = 3;
          *(_WORD *)(v5 + 154) = 6;
          goto LABEL_4;
        }
      }
    }
    else
    {
      v2 = tip2::details::reason_string((tip2::details *)"reason::start_trace_failed", a2);
      v5 = *(_QWORD *)(v8 + 8);
      if ( *(_BYTE *)(v5 + 152) == v9 )
      {
        *(_BYTE *)(v5 + 152) = 3;
        *(_WORD *)(v5 + 154) = 5;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v2 = tip2::details::reason_string((tip2::details *)"reason::get_traces_path_failed", a2);
    v5 = *(_QWORD *)(v6 + 8);
    if ( *(_BYTE *)(v5 + 152) == v7 )
    {
      *(_BYTE *)(v5 + 152) = 3;
      *(_WORD *)(v5 + 154) = 4;
LABEL_4:
      *(_QWORD *)(v5 + 160) = v2;
    }
  }
}

```

## disassembly

```asm
0x18000d284  sub     rsp, 28h
0x18000d288  xor     r9d, r9d
0x18000d28b  mov     r8, rcx
0x18000d28e  cmp     [rcx+10h], r9b
0x18000d292  jnz     short loc_18000D2CE
0x18000d294  lea     rcx, aReasonScenario; "reason::scenario_inactive"
0x18000d29b  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d2a0  mov     rdx, [r8+8]; char *
0x18000d2a4  cmp     [rdx+98h], r9b
0x18000d2ab  jnz     loc_18000D5E0
0x18000d2b1  lea     ecx, [r9+3]
0x18000d2b5  mov     [rdx+98h], cl
0x18000d2bb  mov     [rdx+9Ah], cx
0x18000d2c2  mov     [rdx+0A0h], rax
0x18000d2c9  jmp     loc_18000D5E0
0x18000d2ce  cmp     [rcx+11h], r9b
0x18000d2d2  jnz     short loc_18000D303
0x18000d2d4  lea     rcx, aReasonGetTrace; "reason::get_traces_path_failed"
0x18000d2db  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d2e0  mov     rdx, [r8+8]; char *
0x18000d2e4  cmp     [rdx+98h], r9b
0x18000d2eb  jnz     loc_18000D5E0
0x18000d2f1  mov     byte ptr [rdx+98h], 3
0x18000d2f8  mov     word ptr [rdx+9Ah], 4
0x18000d301  jmp     short loc_18000D2C2
0x18000d303  cmp     [rcx+12h], r9b
0x18000d307  jnz     short loc_18000D338
0x18000d309  lea     rcx, aReasonStartTra; "reason::start_trace_failed"
0x18000d310  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d315  mov     rdx, [r8+8]; char *
0x18000d319  cmp     [rdx+98h], r9b
0x18000d320  jnz     loc_18000D5E0
0x18000d326  mov     byte ptr [rdx+98h], 3
0x18000d32d  mov     word ptr [rdx+9Ah], 5
0x18000d336  jmp     short loc_18000D2C2
0x18000d338  cmp     [rcx+13h], r9b
0x18000d33c  jnz     short loc_18000D370
0x18000d33e  lea     rcx, aReasonEnsureTr; "reason::ensure_traces_folder_failed"
0x18000d345  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d34a  mov     rdx, [r8+8]; char *
0x18000d34e  cmp     [rdx+98h], r9b
0x18000d355  jnz     loc_18000D5E0
0x18000d35b  mov     byte ptr [rdx+98h], 3
0x18000d362  mov     word ptr [rdx+9Ah], 6
0x18000d36b  jmp     loc_18000D2C2
0x18000d370  cmp     [rcx+14h], r9b
0x18000d374  jnz     short loc_18000D3A8
0x18000d376  lea     rcx, aReasonGetTempP; "reason::get_temp_path_failed"
0x18000d37d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d382  mov     rdx, [r8+8]; char *
0x18000d386  cmp     [rdx+98h], r9b
0x18000d38d  jnz     loc_18000D5E0
0x18000d393  mov     byte ptr [rdx+98h], 3
0x18000d39a  mov     word ptr [rdx+9Ah], 7
0x18000d3a3  jmp     loc_18000D2C2
0x18000d3a8  cmp     [rcx+15h], r9b
0x18000d3ac  jnz     short loc_18000D3E0
0x18000d3ae  lea     rcx, aReasonStopTrac; "reason::stop_trace_failed"
0x18000d3b5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d3ba  mov     rdx, [r8+8]; char *
0x18000d3be  cmp     [rdx+98h], r9b
0x18000d3c5  jnz     loc_18000D5E0
0x18000d3cb  mov     byte ptr [rdx+98h], 3
0x18000d3d2  mov     word ptr [rdx+9Ah], 8
0x18000d3db  jmp     loc_18000D2C2
0x18000d3e0  cmp     [rcx+16h], r9b
0x18000d3e4  jnz     short loc_18000D418
0x18000d3e6  lea     rcx, aReasonGetOutpu; "reason::get_output_path_failed"
0x18000d3ed  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d3f2  mov     rdx, [r8+8]; char *
0x18000d3f6  cmp     [rdx+98h], r9b
0x18000d3fd  jnz     loc_18000D5E0
0x18000d403  mov     byte ptr [rdx+98h], 3
0x18000d40a  mov     word ptr [rdx+9Ah], 9
0x18000d413  jmp     loc_18000D2C2
0x18000d418  cmp     [rcx+17h], r9b
0x18000d41c  jnz     short loc_18000D450
0x18000d41e  lea     rcx, aReasonEnsureOu; "reason::ensure_output_folder_failed"
0x18000d425  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d42a  mov     rdx, [r8+8]; char *
0x18000d42e  cmp     [rdx+98h], r9b
0x18000d435  jnz     loc_18000D5E0
0x18000d43b  mov     byte ptr [rdx+98h], 3
0x18000d442  mov     word ptr [rdx+9Ah], 0Ah
0x18000d44b  jmp     loc_18000D2C2
0x18000d450  cmp     [rcx+18h], r9b
0x18000d454  jnz     short loc_18000D488
0x18000d456  lea     rcx, aReasonMoveToOu; "reason::move_to_output_folder_failed"
0x18000d45d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d462  mov     rdx, [r8+8]; char *
0x18000d466  cmp     [rdx+98h], r9b
0x18000d46d  jnz     loc_18000D5E0
0x18000d473  mov     byte ptr [rdx+98h], 3
0x18000d47a  mov     word ptr [rdx+9Ah], 0Bh
0x18000d483  jmp     loc_18000D2C2
0x18000d488  cmp     [rcx+19h], r9b
0x18000d48c  jnz     short loc_18000D4C0
0x18000d48e  lea     rcx, aReasonGetZipPa; "reason::get_zip_path_failed"
0x18000d495  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d49a  mov     rdx, [r8+8]; char *
0x18000d49e  cmp     [rdx+98h], r9b
0x18000d4a5  jnz     loc_18000D5E0
0x18000d4ab  mov     byte ptr [rdx+98h], 3
0x18000d4b2  mov     word ptr [rdx+9Ah], 0Ch
0x18000d4bb  jmp     loc_18000D2C2
0x18000d4c0  cmp     [rcx+1Ah], r9b
0x18000d4c4  jnz     short loc_18000D4F8
0x18000d4c6  lea     rcx, aReasonGetFileT; "reason::get_file_token_failed"
0x18000d4cd  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d4d2  mov     rdx, [r8+8]; char *
0x18000d4d6  cmp     [rdx+98h], r9b
0x18000d4dd  jnz     loc_18000D5E0
0x18000d4e3  mov     byte ptr [rdx+98h], 3
0x18000d4ea  mov     word ptr [rdx+9Ah], 0Dh
0x18000d4f3  jmp     loc_18000D2C2
0x18000d4f8  cmp     [rcx+1Bh], r9b
0x18000d4fc  jnz     short loc_18000D530
0x18000d4fe  lea     rcx, aReasonCompleti; "reason::completion_toast_failed"
0x18000d505  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d50a  mov     rdx, [r8+8]; char *
0x18000d50e  cmp     [rdx+98h], r9b
0x18000d515  jnz     loc_18000D5E0
0x18000d51b  mov     byte ptr [rdx+98h], 3
0x18000d522  mov     word ptr [rdx+9Ah], 0Eh
0x18000d52b  jmp     loc_18000D2C2
0x18000d530  cmp     [rcx+1Ch], r9b
0x18000d534  jnz     short loc_18000D568
0x18000d536  lea     rcx, aReasonStarting; "reason::starting_toast_failed"
0x18000d53d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d542  mov     rdx, [r8+8]; char *
0x18000d546  cmp     [rdx+98h], r9b
0x18000d54d  jnz     loc_18000D5E0
0x18000d553  mov     byte ptr [rdx+98h], 3
0x18000d55a  mov     word ptr [rdx+9Ah], 0Fh
0x18000d563  jmp     loc_18000D2C2
0x18000d568  cmp     [rcx+1Dh], r9b
0x18000d56c  jnz     short loc_18000D59C
0x18000d56e  lea     rcx, aReasonErrorToa; "reason::error_toast_failed"
0x18000d575  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18000d57a  mov     rdx, [r8+8]
0x18000d57e  cmp     [rdx+98h], r9b
0x18000d585  jnz     short loc_18000D5E0
0x18000d587  mov     byte ptr [rdx+98h], 3
0x18000d58e  mov     word ptr [rdx+9Ah], 10h
0x18000d597  jmp     loc_18000D2C2
0x18000d59c  mov     rax, [rcx+8]
0x18000d5a0  test    dword ptr [rax+38h], 200h
0x18000d5a7  mov     cl, [rax+98h]
0x18000d5ad  jnz     short loc_18000D5C5
0x18000d5af  test    cl, cl
0x18000d5b1  jnz     short loc_18000D5E0
0x18000d5b3  mov     byte ptr [rax+98h], 3
0x18000d5ba  mov     word ptr [rax+9Ah], 4001h
0x18000d5c3  jmp     short loc_18000D5D9
0x18000d5c5  test    cl, cl
0x18000d5c7  jnz     short loc_18000D5E0
0x18000d5c9  mov     byte ptr [rax+98h], 1
0x18000d5d0  mov     word ptr [rax+9Ah], 8000h
0x18000d5d9  mov     [rax+0A0h], r9
0x18000d5e0  add     rsp, 28h
0x18000d5e4  retn
```
