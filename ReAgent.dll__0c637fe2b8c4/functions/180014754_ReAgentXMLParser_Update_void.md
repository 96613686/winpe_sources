# ReAgentXMLParser::Update(void)

- ea: `0x180014754`
- end: `0x1800157f6`
- name: `?Update@ReAgentXMLParser@@QEAAKXZ`
- size: `4258`
- prototype: `unsigned int __fastcall(ReAgentXMLParser *__hidden this)`
- caller_count: `20`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012ae0`
- `0x1800174a0`
- `0x180018870`
- `0x180019a90`
- `0x18001e0e0`
- `0x18001fd7c`
- `0x180024a10`
- `0x180024ff0`
- `0x180025560`
- `0x180025a60`
- `0x180026460`
- `0x180026670`
- `0x180029210`
- `0x18002a570`
- `0x18002b844`
- `0x18002c810`
- `0x18002cab4`
- `0x18002d754`
- `0x18003af14`
- `0x18003bfbc`

## callees

- `0x1800059fc`
- `0x18000f698`
- `0x180014754`
- `0x180016164`
- `0x18001670c`
- `0x180016848`
- `0x180016a50`
- `0x180016ce8`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800157bf`
- `ntdll!RtlNtStatusToDosError` at `0x1800157bf`
- `ServicingCommon!RtlFreeLUtf8String` at `0x1800157d1`
- `ServicingCommon!RtlFreeLUtf8String` at `0x1800157d1`

## string_xrefs

- `0x1800157a3`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x1800147a0`: `failed to write EOL`
- `0x1800148e8`: `failed to write EOL`
- `0x180014947`: `failed to write EOL`
- `0x180014abe`: `failed to write EOL`
- `0x180014c2d`: `failed to write EOL`
- `0x180014e0b`: `failed to write EOL`
- `0x180014fe9`: `failed to write EOL`
- `0x18001505a`: `failed to write EOL`
- `0x1800150c4`: `failed to write EOL`
- `0x18001512e`: `failed to write EOL`
- `0x180015198`: `failed to write EOL`
- `0x180015202`: `failed to write EOL`
- `0x180015265`: `failed to write EOL`
- `0x1800152cf`: `failed to write EOL`
- `0x180015330`: `failed to write EOL`
- `0x18001539a`: `failed to write EOL`
- `0x180015409`: `failed to write EOL`
- `0x180015473`: `failed to write EOL`
- `0x1800155ec`: `failed to write EOL`
- `0x18001565c`: `failed to write EOL`
- `0x1800156c6`: `failed to write EOL`
- `0x18001570b`: `failed to write EOL`
- `0x18001579c`: `ReAgentXMLParser::Update %s (0x%x) in file %S line %d`
- `0x1800147d5`: `failed to begin open element`
- `0x180014977`: `failed to begin open element`
- `0x180014aee`: `failed to begin open element`
- `0x1800154ad`: `failed to begin open element`
- `0x18001486c`: `ReAgentXMLParser::Update XML version 0X%X not known, assuming this is a ver 2.0`
- `0x1800148c9`: `failed to end open element`
- `0x180014a9f`: `failed to end open element`
- `0x180014c0e`: `failed to end open element`
- `0x180014dec`: `failed to end open element`
- `0x180014fca`: `failed to end open element`
- `0x180014928`: `failed to write single node`
- `0x18001503b`: `failed to write single node`
- `0x1800150a5`: `failed to write single node`
- `0x18001510f`: `failed to write single node`
- `0x180015179`: `failed to write single node`
- `0x1800151e3`: `failed to write single node`
- `0x180015246`: `failed to write single node`
- `0x1800152b0`: `failed to write single node`
- `0x180015311`: `failed to write single node`
- `0x18001537b`: `failed to write single node`
- `0x1800153ea`: `failed to write single node`
- `0x180015454`: `failed to write single node`
- `0x18001563d`: `failed to write single node`
- `0x1800156a7`: `failed to write single node`
- `0x1800149b6`: `failed to write winre location attribute`
- `0x1800149fb`: `failed to write id attribute`
- `0x180014b6a`: `failed to write id attribute`
- `0x180014d02`: `failed to write id attribute`
- `0x180014ee0`: `failed to write id attribute`
- `0x180015529`: `failed to write id attribute`
- `0x180014a38`: `failed to write offset attribute`
- `0x180014ba7`: `failed to write offset attribute`
- `0x180014d3f`: `failed to write offset attribute`
- `0x180014f1d`: `failed to write offset attribute`
- `0x180015566`: `failed to write offset attribute`
- `0x180014a75`: `failed to write disk id attribute`
- `0x180014be4`: `failed to write disk id attribute`
- `0x180014d7c`: `failed to write disk id attribute`
- `0x180014f5a`: `failed to write disk id attribute`
- `0x1800155a3`: `failed to write disk id attribute`
- `0x180014b25`: `failed to write image location attribute`
- `0x180014c63`: `failed to bein open element os install location`
- `0x180014c86`: `failed to bein open element PBR image location`
- `0x180014cbd`: `failed to write os install location attribute`
- `0x180014dc2`: `failed to write index attribute`
- `0x180014fa0`: `failed to write index attribute`
- `0x180014e41`: `failed to begin open element custom image location`
- `0x180014e64`: `failed to begin open element PBR custom image location`
- `0x180014e9b`: `failed to write custom image location attribute`
- `0x1800154e4`: `failed to write path attribute`
- `0x1800155cd`: `failed to write end open element`
- `0x1800156ec`: `failed to write child nodes`
- `0x180015790`: `failed to update original file for copied xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReAgentXMLParser::Update(ReAgentXMLParser *this)
{
  NTSTATUS v2; // edi
  const wchar_t *v3; // r8
  int v4; // esi
  int v5; // r8d
  const struct _LUTF8_STRING *v6; // r9
  const struct _LUTF8_STRING *v7; // r8
  const struct _LUTF8_STRING *v8; // r8
  const struct _LUTF8_STRING *v9; // r8
  const struct _LUTF8_STRING *v10; // r8
  const struct _LUTF8_STRING *v11; // r8
  const struct _LUTF8_STRING *v12; // r8
  const struct _LUTF8_STRING *v13; // r8
  const struct _LUTF8_STRING *v14; // r8
  __int64 v15; // rcx
  __int64 (__fastcall *v16)(__int64, _QWORD, void *); // rax
  const struct _LUTF8_STRING *v17; // r8
  const struct _LUTF8_STRING *v18; // r8
  const struct _LUTF8_STRING *v19; // r8
  const struct _LUTF8_STRING *v20; // r8
  const struct _LUTF8_STRING *v21; // r8
  __int64 v22; // rcx
  __int64 (__fastcall *v23)(__int64, _QWORD, void *); // rax
  const struct _LUTF8_STRING *v24; // r8
  const struct _LUTF8_STRING *v25; // r8
  const struct _LUTF8_STRING *v26; // r8
  const struct _LUTF8_STRING *v27; // r8
  const struct _LUTF8_STRING *v28; // r8
  const struct _LUTF8_STRING *v29; // r9
  const struct _LUTF8_STRING *v30; // r9
  const struct _LUTF8_STRING *v31; // r9
  const struct _LUTF8_STRING *v32; // r9
  const struct _LUTF8_STRING *v33; // r9
  const struct _LUTF8_STRING *v34; // r9
  const struct _LUTF8_STRING *v35; // r9
  const struct _LUTF8_STRING *v36; // r9
  const struct _LUTF8_STRING *v37; // r9
  const struct _LUTF8_STRING *v38; // r9
  const struct _LUTF8_STRING *v39; // r9
  const struct _LUTF8_STRING *v40; // r8
  const struct _LUTF8_STRING *v41; // r8
  const struct _LUTF8_STRING *v42; // r8
  const struct _LUTF8_STRING *v43; // r8
  ULONG v44; // esi
  struct _GUID *v46; // [rsp+28h] [rbp-50h]
  unsigned __int64 v47[2]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v48; // [rsp+50h] [rbp-28h] BYREF
  __int64 v49; // [rsp+60h] [rbp-18h]

  v47[1] = -2;
  v48 = 0;
  v49 = 0;
  v2 = ReAgentXMLParser::WriteEOL(this);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
           *((_QWORD *)this + 5),
           0,
           &ReAgentXMLParser::Utf8ToplevelEntryTag);
    if ( v2 >= 0 )
    {
      v5 = *((_DWORD *)this + 7);
      if ( v5 == 1 )
      {
        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, void *))(**((_QWORD **)this + 5) + 112LL))(
               *((_QWORD *)this + 5),
               0,
               &ReAgentXMLParser::Utf8VersionAttrTag,
               &ReAgentXMLParser::Utf8ConfigVersionValVer1);
        if ( v2 < 0 )
        {
          v3 = L"failed to emit attribute";
          v4 = 489;
          goto LABEL_166;
        }
      }
      else if ( v5 == 2 )
      {
        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, void *))(**((_QWORD **)this + 5) + 112LL))(
               *((_QWORD *)this + 5),
               0,
               &ReAgentXMLParser::Utf8VersionAttrTag,
               &ReAgentXMLParser::Utf8ConfigVersionValVer2);
        if ( v2 < 0 )
        {
          v3 = L"failed to emit attribute";
          v4 = 493;
          goto LABEL_166;
        }
      }
      else
      {
        UnattendLogW(0, L"ReAgentXMLParser::Update XML version 0X%X not known, assuming this is a ver 2.0");
        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, void *))(**((_QWORD **)this + 5) + 112LL))(
               *((_QWORD *)this + 5),
               0,
               &ReAgentXMLParser::Utf8VersionAttrTag,
               &ReAgentXMLParser::Utf8ConfigVersionValVer2);
        if ( v2 < 0 )
        {
          v3 = L"failed to emit attribute";
          v4 = 498;
          goto LABEL_166;
        }
      }
      v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5), 0);
      if ( v2 >= 0 )
      {
        v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
        if ( v2 >= 0 )
        {
          v2 = ReAgentXMLParser::WriteSingleNode(
                 this,
                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8BCDEntryTag,
                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
                 v6,
                 0,
                 *((struct _GUID **)this + 8),
                 0);
          if ( v2 >= 0 )
          {
            v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
                     *((_QWORD *)this + 5),
                     0,
                     &ReAgentXMLParser::Utf8WinreLocationTag);
              if ( v2 >= 0 )
              {
                v4 = 620;
                v2 = ReAgentXMLParser::WriteAttribute(
                       this,
                       (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag,
                       v7,
                       (unsigned __int16 *)(*((_QWORD *)this + 8) + 620LL),
                       0,
                       0);
                if ( v2 >= 0 )
                {
                  v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 1224LL);
                  v2 = ReAgentXMLParser::WriteAttribute(
                         this,
                         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
                         v8,
                         0,
                         0,
                         v47);
                  if ( v2 >= 0 )
                  {
                    v2 = ReAgentXMLParser::WriteAttribute(
                           this,
                           (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OffsetAttrTag,
                           v9,
                           0,
                           0,
                           (unsigned __int64 *)(*((_QWORD *)this + 8) + 1248LL));
                    if ( v2 >= 0 )
                    {
                      v2 = ReAgentXMLParser::WriteAttribute(
                             this,
                             (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8GuidAttrTag,
                             v10,
                             0,
                             (struct _GUID *)(*((_QWORD *)this + 8) + 1228LL),
                             0);
                      if ( v2 >= 0 )
                      {
                        v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(
                               *((_QWORD *)this + 5),
                               1);
                        if ( v2 >= 0 )
                        {
                          v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                          if ( v2 >= 0 )
                          {
                            v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(
                                   *((_QWORD *)this + 5),
                                   0,
                                   &ReAgentXMLParser::Utf8ImageLocationTag);
                            if ( v2 >= 0 )
                            {
                              v2 = ReAgentXMLParser::WriteAttribute(
                                     this,
                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag,
                                     v11,
                                     (unsigned __int16 *)(*((_QWORD *)this + 8) + 1860LL),
                                     0,
                                     0);
                              if ( v2 >= 0 )
                              {
                                v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 2464LL);
                                v2 = ReAgentXMLParser::WriteAttribute(
                                       this,
                                       (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
                                       v12,
                                       0,
                                       0,
                                       v47);
                                if ( v2 >= 0 )
                                {
                                  v2 = ReAgentXMLParser::WriteAttribute(
                                         this,
                                         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OffsetAttrTag,
                                         v13,
                                         0,
                                         0,
                                         (unsigned __int64 *)(*((_QWORD *)this + 8) + 2488LL));
                                  if ( v2 >= 0 )
                                  {
                                    v2 = ReAgentXMLParser::WriteAttribute(
                                           this,
                                           (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8GuidAttrTag,
                                           v14,
                                           0,
                                           (struct _GUID *)(*((_QWORD *)this + 8) + 2468LL),
                                           0);
                                    if ( v2 >= 0 )
                                    {
                                      v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(
                                             *((_QWORD *)this + 5),
                                             1);
                                      if ( v2 >= 0 )
                                      {
                                        v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                        if ( v2 >= 0 )
                                        {
                                          v15 = *((_QWORD *)this + 5);
                                          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v15 + 40LL);
                                          if ( *((_DWORD *)this + 7) == 1 )
                                          {
                                            v2 = v16(v15, 0, &ReAgentXMLParser::Utf8OsInstallLocationTag);
                                            if ( v2 < 0 )
                                            {
                                              v3 = L"failed to bein open element os install location";
                                              v4 = 545;
                                              goto LABEL_166;
                                            }
                                          }
                                          else
                                          {
                                            v2 = v16(v15, 0, &ReAgentXMLParser::Utf8PBRImageLocationTag);
                                            if ( v2 < 0 )
                                            {
                                              v3 = L"failed to bein open element PBR image location";
                                              v4 = 549;
                                              goto LABEL_166;
                                            }
                                          }
                                          v2 = ReAgentXMLParser::WriteAttribute(
                                                 this,
                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag,
                                                 v17,
                                                 (unsigned __int16 *)(*((_QWORD *)this + 8) + 3100LL),
                                                 0,
                                                 0);
                                          if ( v2 >= 0 )
                                          {
                                            v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 3704LL);
                                            v2 = ReAgentXMLParser::WriteAttribute(
                                                   this,
                                                   (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
                                                   v18,
                                                   0,
                                                   0,
                                                   v47);
                                            if ( v2 >= 0 )
                                            {
                                              v2 = ReAgentXMLParser::WriteAttribute(
                                                     this,
                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OffsetAttrTag,
                                                     v19,
                                                     0,
                                                     0,
                                                     (unsigned __int64 *)(*((_QWORD *)this + 8) + 3728LL));
                                              if ( v2 >= 0 )
                                              {
                                                v2 = ReAgentXMLParser::WriteAttribute(
                                                       this,
                                                       (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8GuidAttrTag,
                                                       v20,
                                                       0,
                                                       (struct _GUID *)(*((_QWORD *)this + 8) + 3708LL),
                                                       0);
                                                if ( v2 >= 0 )
                                                {
                                                  v47[0] = *(int *)(*((_QWORD *)this + 8) + 5580LL);
                                                  v2 = ReAgentXMLParser::WriteAttribute(
                                                         this,
                                                         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IndexAttrTag,
                                                         v21,
                                                         0,
                                                         0,
                                                         v47);
                                                  if ( v2 >= 0 )
                                                  {
                                                    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(
                                                           *((_QWORD *)this + 5),
                                                           1);
                                                    if ( v2 >= 0 )
                                                    {
                                                      v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                      if ( v2 >= 0 )
                                                      {
                                                        v22 = *((_QWORD *)this + 5);
                                                        v23 = *(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v22 + 40LL);
                                                        if ( *((_DWORD *)this + 7) == 1 )
                                                        {
                                                          v2 = v23(
                                                                 v22,
                                                                 0,
                                                                 &ReAgentXMLParser::Utf8CustomImageLocationTag);
                                                          if ( v2 < 0 )
                                                          {
                                                            v3 = L"failed to begin open element custom image location";
                                                            v4 = 570;
                                                            goto LABEL_166;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v2 = v23(
                                                                 v22,
                                                                 0,
                                                                 &ReAgentXMLParser::Utf8PBRCustomImageLocationTag);
                                                          if ( v2 < 0 )
                                                          {
                                                            v3 = L"failed to begin open element PBR custom image location";
                                                            v4 = 574;
                                                            goto LABEL_166;
                                                          }
                                                        }
                                                        v2 = ReAgentXMLParser::WriteAttribute(
                                                               this,
                                                               (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag,
                                                               v24,
                                                               (unsigned __int16 *)(*((_QWORD *)this + 8) + 4340LL),
                                                               0,
                                                               0);
                                                        if ( v2 >= 0 )
                                                        {
                                                          v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 3704LL);
                                                          v2 = ReAgentXMLParser::WriteAttribute(
                                                                 this,
                                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag,
                                                                 v25,
                                                                 0,
                                                                 0,
                                                                 v47);
                                                          if ( v2 >= 0 )
                                                          {
                                                            v2 = ReAgentXMLParser::WriteAttribute(
                                                                   this,
                                                                   (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OffsetAttrTag,
                                                                   v26,
                                                                   0,
                                                                   0,
                                                                   (unsigned __int64 *)(*((_QWORD *)this + 8) + 4968LL));
                                                            if ( v2 >= 0 )
                                                            {
                                                              v2 = ReAgentXMLParser::WriteAttribute(
                                                                     this,
                                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8GuidAttrTag,
                                                                     v27,
                                                                     0,
                                                                     (struct _GUID *)(*((_QWORD *)this + 8) + 4948LL),
                                                                     0);
                                                              if ( v2 >= 0 )
                                                              {
                                                                v47[0] = *(int *)(*((_QWORD *)this + 8) + 5584LL);
                                                                v2 = ReAgentXMLParser::WriteAttribute(
                                                                       this,
                                                                       (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IndexAttrTag,
                                                                       v28,
                                                                       0,
                                                                       0,
                                                                       v47);
                                                                if ( v2 >= 0 )
                                                                {
                                                                  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(
                                                                         *((_QWORD *)this + 5),
                                                                         1);
                                                                  if ( v2 >= 0 )
                                                                  {
                                                                    v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                    if ( v2 >= 0 )
                                                                    {
                                                                      v47[0] = *(int *)(*((_QWORD *)this + 8) + 5588LL);
                                                                      v2 = ReAgentXMLParser::WriteSingleNode(
                                                                             this,
                                                                             (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8InstallStateTag,
                                                                             (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                             v29,
                                                                             0,
                                                                             0,
                                                                             v47);
                                                                      if ( v2 >= 0 )
                                                                      {
                                                                        v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                        if ( v2 >= 0 )
                                                                        {
                                                                          v47[0] = *(int *)(*((_QWORD *)this + 8)
                                                                                          + 5592LL);
                                                                          v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                 this,
                                                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OSInstallAvTag,
                                                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                                 v30,
                                                                                 0,
                                                                                 0,
                                                                                 v47);
                                                                          if ( v2 >= 0 )
                                                                          {
                                                                            v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                            if ( v2 >= 0 )
                                                                            {
                                                                              v47[0] = *(int *)(*((_QWORD *)this + 8)
                                                                                              + 5596LL);
                                                                              v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                     this,
                                                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8CustomImageAvTag,
                                                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                                     v31,
                                                                                     0,
                                                                                     0,
                                                                                     v47);
                                                                              if ( v2 >= 0 )
                                                                              {
                                                                                v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                if ( v2 >= 0 )
                                                                                {
                                                                                  v47[0] = *(int *)(*((_QWORD *)this + 8)
                                                                                                  + 6228LL);
                                                                                  v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                         this,
                                                                                         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IsAutoRepairOnTag,
                                                                                         (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                                         v32,
                                                                                         0,
                                                                                         0,
                                                                                         v47);
                                                                                  if ( v2 >= 0 )
                                                                                  {
                                                                                    v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                    if ( v2 >= 0 )
                                                                                    {
                                                                                      v47[0] = *(int *)(*((_QWORD *)this + 8) + 5604LL);
                                                                                      v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                             this,
                                                                                             (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8WinreStaged,
                                                                                             (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                                             v33,
                                                                                             0,
                                                                                             0,
                                                                                             v47);
                                                                                      if ( v2 >= 0 )
                                                                                      {
                                                                                        v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                        if ( v2 >= 0 )
                                                                                        {
                                                                                          v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                                 this,
                                                                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OperationParamTag,
                                                                                                 (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag,
                                                                                                 v34,
                                                                                                 (unsigned __int16 *)(*((_QWORD *)this + 8) + 5616LL),
                                                                                                 0,
                                                                                                 0);
                                                                                          if ( v2 >= 0 )
                                                                                          {
                                                                                            v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                            if ( v2 >= 0 )
                                                                                            {
                                                                                              v47[0] = *(int *)(*((_QWORD *)this + 8) + 6220LL);
                                                                                              v2 = ReAgentXMLParser::WriteSingleNode(
                                                                                                     this,
                                                                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OperationPermanentTag,
                                                                                                     (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag,
                                                                                                     v35,
                                                                                                     0,
                                                                                                     0,
                                                                                                     v47);
                                                                                              if ( v2 >= 0 )
                                                                                              {
                                                                                                v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                if ( v2 >= 0 )
                                                                                                {
                                                                                                  v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OsBuildVersion, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag, v36, (unsigned __int16 *)(*((_QWORD *)this + 8) + 4976LL), 0, 0);
                                                                                                  if ( v2 >= 0 )
                                                                                                  {
                                                                                                    v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                    if ( v2 >= 0 )
                                                                                                    {
                                                                                                      v47[0] = *(int *)(*((_QWORD *)this + 8) + 5600LL);
                                                                                                      v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OemTool, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag, v37, 0, 0, v47);
                                                                                                      if ( v2 >= 0 )
                                                                                                      {
                                                                                                        v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                        if ( v2 >= 0 )
                                                                                                        {
                                                                                                          if ( *((_DWORD *)this + 7) == 1 )
                                                                                                          {
                                                                                                            v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 6224LL);
                                                                                                            v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8BootKey, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag, v38, 0, 0, v47);
                                                                                                            if ( v2 < 0 )
                                                                                                            {
                                                                                                              v3 = L"failed to write single node";
                                                                                                              v4 = 649;
                                                                                                              goto LABEL_166;
                                                                                                            }
                                                                                                            v2 = ReAgentXMLParser::WriteEOL(this);
                                                                                                            if ( v2 < 0 )
                                                                                                            {
                                                                                                              v3 = L"failed to write EOL";
                                                                                                              v4 = 650;
                                                                                                              goto LABEL_166;
                                                                                                            }
                                                                                                          }
                                                                                                          v47[0] = *(int *)(*((_QWORD *)this + 8) + 5608LL);
                                                                                                          v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IsServer, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag, v38, 0, 0, v47);
                                                                                                          if ( v2 >= 0 )
                                                                                                          {
                                                                                                            v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                            if ( v2 >= 0 )
                                                                                                            {
                                                                                                              if ( *((_DWORD *)this + 7) != 1 )
                                                                                                              {
                                                                                                                v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5), 0, &ReAgentXMLParser::Utf8DownlevelWinreLocationTag);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to begin open element";
                                                                                                                  v4 = 662;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v2 = ReAgentXMLParser::WriteAttribute(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8PathAttrTag, v40, (unsigned __int16 *)(*((_QWORD *)this + 8) + 6836LL), 0, 0);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write path attribute";
                                                                                                                  v4 = 664;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v47[0] = *(unsigned int *)(*((_QWORD *)this + 8) + 7440LL);
                                                                                                                v2 = ReAgentXMLParser::WriteAttribute(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IdAttrTag, v41, 0, 0, v47);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write id attribute";
                                                                                                                  v4 = 666;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v2 = ReAgentXMLParser::WriteAttribute(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8OffsetAttrTag, v42, 0, 0, (unsigned __int64 *)(*((_QWORD *)this + 8) + 7464LL));
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write offset attribute";
                                                                                                                  v4 = 668;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v2 = ReAgentXMLParser::WriteAttribute(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8GuidAttrTag, v43, 0, (struct _GUID *)(*((_QWORD *)this + 8) + 7444LL), 0);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write disk id attribute";
                                                                                                                  v4 = 670;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 48LL))(*((_QWORD *)this + 5), 1);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write end open element";
                                                                                                                  v4 = 671;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                                if ( v2 < 0 )
                                                                                                                {
                                                                                                                  v3 = L"failed to write EOL";
                                                                                                                  v4 = 672;
                                                                                                                  goto LABEL_166;
                                                                                                                }
                                                                                                                if ( *((_DWORD *)this + 7) != 1 )
                                                                                                                {
                                                                                                                  v47[0] = *(int *)(*((_QWORD *)this + 8) + 7472LL);
                                                                                                                  v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8IsWimBoot, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag, v39, 0, 0, v47);
                                                                                                                  if ( v2 < 0 )
                                                                                                                  {
                                                                                                                    v3 = L"failed to write single node";
                                                                                                                    v4 = 680;
                                                                                                                    goto LABEL_166;
                                                                                                                  }
                                                                                                                  v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                                  if ( v2 < 0 )
                                                                                                                  {
                                                                                                                    v3 = L"failed to write EOL";
                                                                                                                    v4 = 681;
                                                                                                                    goto LABEL_166;
                                                                                                                  }
                                                                                                                }
                                                                                                              }
                                                                                                              v47[0] = *(int *)(*((_QWORD *)this + 8) + 7476LL);
                                                                                                              v2 = ReAgentXMLParser::WriteSingleNode(this, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8NarratorScheduledTag, (const struct _LUTF8_STRING *)&ReAgentXMLParser::Utf8StateAttrTag, v39, 0, 0, v47);
                                                                                                              if ( v2 >= 0 )
                                                                                                              {
                                                                                                                v2 = ReAgentXMLParser::WriteEOLWithIndent(this);
                                                                                                                if ( v2 >= 0 )
                                                                                                                {
                                                                                                                  v2 = (*(__int64 (__fastcall **)(ReAgentXMLParser *))(*(_QWORD *)this + 32LL))(this);
                                                                                                                  if ( v2 >= 0 )
                                                                                                                  {
                                                                                                                    v2 = ReAgentXMLParser::WriteEOL(this);
                                                                                                                    if ( v2 >= 0 )
                                                                                                                    {
                                                                                                                      v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *))(**((_QWORD **)this + 5) + 80LL))(*((_QWORD *)this + 5), 0, &ReAgentXMLParser::Utf8ToplevelEntryTag);
                                                                                                                      if ( v2 >= 0 )
                                                                                                                      {
                                                                                                                        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7), 0, &v48);
                                                                                                                        if ( v2 >= 0 )
                                                                                                                        {
                                                                                                                          v44 = ReAgentXMLParser::WriteXMLFile(this, (struct _LUTF8_STRING *)&v48);
                                                                                                                          v2 = WinreUpdateForCopiedConfigFile(*((LPCWSTR *)this + 1));
                                                                                                                          if ( v2 >= 0 )
                                                                                                                            goto LABEL_167;
                                                                                                                          v3 = L"failed to update original file for copied xml";
                                                                                                                          v4 = 714;
                                                                                                                        }
                                                                                                                        else
                                                                                                                        {
                                                                                                                          v3 = L"failed to get data and reset";
                                                                                                                          v4 = 707;
                                                                                                                        }
                                                                                                                      }
                                                                                                                      else
                                                                                                                      {
                                                                                                                        v3 = L"failed to close element";
                                                                                                                        v4 = 701;
                                                                                                                      }
                                                                                                                    }
                                                                                                                    else
                                                                                                                    {
                                                                                                                      v3 = L"failed to write EOL";
                                                                                                                      v4 = 695;
                                                                                                                    }
                                                                                                                  }
                                                                                                                  else
                                                                                                                  {
                                                                                                                    v3 = L"failed to write child nodes";
                                                                                                                    v4 = 694;
                                                                                                                  }
                                                                                                                }
                                                                                                                else
                                                                                                                {
                                                                                                                  v3 = L"failed to write EOL";
                                                                                                                  v4 = 688;
                                                                                                                }
                                                                                                              }
                                                                                                              else
                                                                                                              {
                                                                                                                v3 = L"failed to write single node";
                                                                                                                v4 = 687;
                                                                                                              }
                                                                                                            }
                                                                                                            else
                                                                                                            {
                                                                                                              v3 = L"failed to write EOL";
                                                                                                              v4 = 657;
                                                                                                            }
                                                                                                          }
                                                                                                          else
                                                                                                          {
                                                                                                            v3 = L"failed to write single node";
                                                                                                            v4 = 656;
                                                                                                          }
                                                                                                        }
                                                                                                        else
                                                                                                        {
                                                                                                          v3 = L"failed to write EOL";
                                                                                                          v4 = 642;
                                                                                                        }
                                                                                                      }
                                                                                                      else
                                                                                                      {
                                                                                                        v3 = L"failed to write single node";
                                                                                                        v4 = 641;
                                                                                                      }
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      v3 = L"failed to write EOL";
                                                                                                      v4 = 636;
                                                                                                    }
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    v3 = L"failed to write single node";
                                                                                                    v4 = 635;
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  v3 = L"failed to write EOL";
                                                                                                  v4 = 631;
                                                                                                }
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                v3 = L"failed to write single node";
                                                                                                v4 = 630;
                                                                                              }
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              v3 = L"failed to write EOL";
                                                                                              v4 = 625;
                                                                                            }
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            v3 = L"failed to write single node";
                                                                                            v4 = 624;
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v3 = L"failed to write EOL";
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v3 = L"failed to write single node";
                                                                                        v4 = 619;
                                                                                      }
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v3 = L"failed to write EOL";
                                                                                      v4 = 614;
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v3 = L"failed to write single node";
                                                                                    v4 = 613;
                                                                                  }
                                                                                }
                                                                                else
                                                                                {
                                                                                  v3 = L"failed to write EOL";
                                                                                  v4 = 608;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v3 = L"failed to write single node";
                                                                                v4 = 607;
                                                                              }
                                                                            }
                                                                            else
                                                                            {
                                                                              v3 = L"failed to write EOL";
                                                                              v4 = 602;
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            v3 = L"failed to write single node";
                                                                            v4 = 601;
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          v3 = L"failed to write EOL";
                                                                          v4 = 596;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v3 = L"failed to write single node";
                                                                        v4 = 595;
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      v3 = L"failed to write EOL";
                                                                      v4 = 589;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v3 = L"failed to end open element";
                                                                    v4 = 588;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v3 = L"failed to write index attribute";
                                                                  v4 = 587;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v3 = L"failed to write disk id attribute";
                                                                v4 = 584;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v3 = L"failed to write offset attribute";
                                                              v4 = 582;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v3 = L"failed to write id attribute";
                                                            v4 = 580;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v3 = L"failed to write custom image location attribute";
                                                          v4 = 578;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v3 = L"failed to write EOL";
                                                        v4 = 564;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v3 = L"failed to end open element";
                                                      v4 = 563;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v3 = L"failed to write index attribute";
                                                    v4 = 562;
                                                  }
                                                }
                                                else
                                                {
                                                  v3 = L"failed to write disk id attribute";
                                                  v4 = 559;
                                                }
                                              }
                                              else
                                              {
                                                v3 = L"failed to write offset attribute";
                                                v4 = 557;
                                              }
                                            }
                                            else
                                            {
                                              v3 = L"failed to write id attribute";
                                              v4 = 555;
                                            }
                                          }
                                          else
                                          {
                                            v3 = L"failed to write os install location attribute";
                                            v4 = 553;
                                          }
                                        }
                                        else
                                        {
                                          v3 = L"failed to write EOL";
                                          v4 = 539;
                                        }
                                      }
                                      else
                                      {
                                        v3 = L"failed to end open element";
                                        v4 = 538;
                                      }
                                    }
                                    else
                                    {
                                      v3 = L"failed to write disk id attribute";
                                      v4 = 537;
                                    }
                                  }
                                  else
                                  {
                                    v3 = L"failed to write offset attribute";
                                    v4 = 535;
                                  }
                                }
                                else
                                {
                                  v3 = L"failed to write id attribute";
                                  v4 = 533;
                                }
                              }
                              else
                              {
                                v3 = L"failed to write image location attribute";
                                v4 = 531;
                              }
                            }
                            else
                            {
                              v3 = L"failed to begin open element";
                              v4 = 529;
                            }
                          }
                          else
                          {
                            v3 = L"failed to write EOL";
                            v4 = 524;
                          }
                        }
                        else
                        {
                          v3 = L"failed to end open element";
                          v4 = 523;
                        }
                      }
                      else
                      {
                        v3 = L"failed to write disk id attribute";
                        v4 = 522;
                      }
                    }
                    else
                    {
                      v3 = L"failed to write offset attribute";
                      v4 = 520;
                    }
                  }
                  else
                  {
                    v3 = L"failed to write id attribute";
                    v4 = 518;
                  }
                }
                else
                {
                  v3 = L"failed to write winre location attribute";
                  v4 = 516;
                }
              }
              else
              {
                v3 = L"failed to begin open element";
                v4 = 514;
              }
            }
            else
            {
              v3 = L"failed to write EOL";
              v4 = 510;
            }
          }
          else
          {
            v3 = L"failed to write single node";
            v4 = 509;
          }
        }
        else
        {
          v3 = L"failed to write EOL";
          v4 = 502;
        }
      }
      else
      {
        v3 = L"failed to end open element";
        v4 = 501;
      }
    }
    else
    {
      v3 = L"failed to begin open element";
      v4 = 486;
    }
  }
  else
  {
    v3 = L"failed to write EOL";
    v4 = 485;
  }
LABEL_166:
  LODWORD(v46) = v4;
  UnattendLogW(
    2,
    L"ReAgentXMLParser::Update %s (0x%x) in file %S line %d",
    v3,
    (unsigned int)v2,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
    v46);
  v44 = RtlNtStatusToDosError(v2);
LABEL_167:
  if ( v49 )
    RtlFreeLUtf8String(&v48);
  return v44;
}

```

## disassembly

```asm
0x180014754  push    rbp
0x180014756  push    rbx
0x180014757  push    rsi
0x180014758  push    rdi
0x180014759  push    r12
0x18001475b  push    r13
0x18001475d  push    r14
0x18001475f  push    r15
0x180014761  mov     rbp, rsp
0x180014764  sub     rsp, 78h
0x180014768  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180014770  mov     rax, cs:__security_cookie
0x180014777  xor     rax, rsp
0x18001477a  mov     [rbp+var_10], rax
0x18001477e  mov     r14, rcx
0x180014781  xorps   xmm0, xmm0
0x180014784  xor     eax, eax
0x180014786  movups  [rbp+var_28], xmm0
0x18001478a  mov     [rbp+var_18], rax
0x18001478e  call    ?WriteEOL@ReAgentXMLParser@@IEAAJXZ; ReAgentXMLParser::WriteEOL(void)
0x180014793  mov     edi, eax
0x180014795  xor     r15d, r15d
0x180014798  test    eax, eax
0x18001479a  jns     short loc_1800147B1
0x18001479c  lea     ebx, [r15+2]
0x1800147a0  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x1800147a7  mov     esi, 1E5h
0x1800147ac  jmp     loc_18001579C
0x1800147b1  mov     rcx, [r14+28h]
0x1800147b5  mov     rax, [rcx]
0x1800147b8  lea     r8, ?Utf8ToplevelEntryTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ToplevelEntryTag
0x1800147bf  xor     edx, edx
0x1800147c1  mov     rax, [rax+28h]
0x1800147c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ca  mov     edi, eax
0x1800147cc  mov     ebx, 2
0x1800147d1  test    eax, eax
0x1800147d3  jns     short loc_1800147E6
0x1800147d5  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x1800147dc  mov     esi, 1E6h
0x1800147e1  jmp     loc_18001579C
0x1800147e6  mov     r8d, [r14+1Ch]
0x1800147ea  mov     r13d, 1
0x1800147f0  cmp     r8d, r13d
0x1800147f3  jnz     short loc_180014830
0x1800147f5  mov     rcx, [r14+28h]
0x1800147f9  mov     rax, [rcx]
0x1800147fc  lea     r9, ?Utf8ConfigVersionValVer1@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ConfigVersionValVer1
0x180014803  lea     r8, ?Utf8VersionAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8VersionAttrTag
0x18001480a  xor     edx, edx
0x18001480c  mov     rax, [rax+70h]
0x180014810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014815  mov     edi, eax
0x180014817  test    eax, eax
0x180014819  jns     loc_1800148B1
0x18001481f  lea     r8, aFailedToEmitAt; "failed to emit attribute"
0x180014826  mov     esi, 1E9h
0x18001482b  jmp     loc_18001579C
0x180014830  cmp     r8d, ebx
0x180014833  jnz     short loc_18001486C
0x180014835  mov     rcx, [r14+28h]
0x180014839  mov     rax, [rcx]
0x18001483c  lea     r9, ?Utf8ConfigVersionValVer2@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ConfigVersionValVer2
0x180014843  lea     r8, ?Utf8VersionAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8VersionAttrTag
0x18001484a  xor     edx, edx
0x18001484c  mov     rax, [rax+70h]
0x180014850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014855  mov     edi, eax
0x180014857  test    eax, eax
0x180014859  jns     short loc_1800148B1
0x18001485b  lea     r8, aFailedToEmitAt; "failed to emit attribute"
0x180014862  mov     esi, 1EDh
0x180014867  jmp     loc_18001579C
0x18001486c  lea     rdx, aReagentxmlpars_2; "ReAgentXMLParser::Update XML version 0X"...
0x180014873  xor     ecx, ecx
0x180014875  call    UnattendLogW
0x18001487a  mov     rcx, [r14+28h]
0x18001487e  mov     rax, [rcx]
0x180014881  lea     r9, ?Utf8ConfigVersionValVer2@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ConfigVersionValVer2
0x180014888  lea     r8, ?Utf8VersionAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8VersionAttrTag
0x18001488f  xor     edx, edx
0x180014891  mov     rax, [rax+70h]
0x180014895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001489a  mov     edi, eax
0x18001489c  test    eax, eax
0x18001489e  jns     short loc_1800148B1
0x1800148a0  lea     r8, aFailedToEmitAt; "failed to emit attribute"
0x1800148a7  mov     esi, 1F2h
0x1800148ac  jmp     loc_18001579C
0x1800148b1  mov     rcx, [r14+28h]
0x1800148b5  mov     rax, [rcx]
0x1800148b8  xor     edx, edx
0x1800148ba  mov     rax, [rax+30h]
0x1800148be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c3  mov     edi, eax
0x1800148c5  test    eax, eax
0x1800148c7  jns     short loc_1800148DA
0x1800148c9  lea     r8, aFailedToEndOpe; "failed to end open element"
0x1800148d0  mov     esi, 1F5h
0x1800148d5  jmp     loc_18001579C
0x1800148da  mov     rcx, r14; this
0x1800148dd  call    ?WriteEOLWithIndent@ReAgentXMLParser@@IEAAJXZ; ReAgentXMLParser::WriteEOLWithIndent(void)
0x1800148e2  mov     edi, eax
0x1800148e4  test    eax, eax
0x1800148e6  jns     short loc_1800148F9
0x1800148e8  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x1800148ef  mov     esi, 1F6h
0x1800148f4  jmp     loc_18001579C
0x1800148f9  mov     [rsp+78h+var_48], r15; unsigned __int64 *
0x1800148fe  mov     rax, [r14+40h]
0x180014902  mov     [rsp+78h+var_50], rax; struct _GUID *
0x180014907  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x18001490c  lea     r8, ?Utf8IdAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014913  lea     rdx, ?Utf8BCDEntryTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x18001491a  mov     rcx, r14; this
0x18001491d  call    ?WriteSingleNode@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@00PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteSingleNode(_LUTF8_STRING const *,_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014922  mov     edi, eax
0x180014924  test    eax, eax
0x180014926  jns     short loc_180014939
0x180014928  lea     r8, aFailedToWriteS_6; "failed to write single node"
0x18001492f  mov     esi, 1FDh
0x180014934  jmp     loc_18001579C
0x180014939  mov     rcx, r14; this
0x18001493c  call    ?WriteEOLWithIndent@ReAgentXMLParser@@IEAAJXZ; ReAgentXMLParser::WriteEOLWithIndent(void)
0x180014941  mov     edi, eax
0x180014943  test    eax, eax
0x180014945  jns     short loc_180014958
0x180014947  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x18001494e  mov     esi, 1FEh
0x180014953  jmp     loc_18001579C
0x180014958  mov     rcx, [r14+28h]
0x18001495c  mov     rax, [rcx]
0x18001495f  lea     r8, ?Utf8WinreLocationTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8WinreLocationTag
0x180014966  xor     edx, edx
0x180014968  mov     rax, [rax+28h]
0x18001496c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014971  mov     edi, eax
0x180014973  test    eax, eax
0x180014975  jns     short loc_180014988
0x180014977  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x18001497e  mov     esi, 202h
0x180014983  jmp     loc_18001579C
0x180014988  mov     r9, [r14+40h]
0x18001498c  mov     esi, 26Ch
0x180014991  add     r9, rsi; unsigned __int16 *
0x180014994  mov     [rsp+78h+var_50], r15; unsigned __int64 *
0x180014999  mov     [rsp+78h+var_58], r15; struct _GUID *
0x18001499e  lea     r12, ?Utf8PathAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8PathAttrTag
0x1800149a5  mov     rdx, r12; struct _LUTF8_STRING *
0x1800149a8  mov     rcx, r14; this
0x1800149ab  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800149b0  mov     edi, eax
0x1800149b2  test    eax, eax
0x1800149b4  jns     short loc_1800149C7
0x1800149b6  lea     r8, aFailedToWriteW_0; "failed to write winre location attribut"...
0x1800149bd  mov     esi, 204h
0x1800149c2  jmp     loc_18001579C
0x1800149c7  mov     rax, [r14+40h]
0x1800149cb  mov     ecx, [rax+4C8h]
0x1800149d1  mov     [rbp+var_38], rcx
0x1800149d5  lea     rax, [rbp+var_38]
0x1800149d9  mov     [rsp+78h+var_50], rax; unsigned __int64 *
0x1800149de  mov     [rsp+78h+var_58], r15; struct _GUID *
0x1800149e3  xor     r9d, r9d; unsigned __int16 *
0x1800149e6  lea     rdx, ?Utf8IdAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x1800149ed  mov     rcx, r14; this
0x1800149f0  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x1800149f5  mov     edi, eax
0x1800149f7  test    eax, eax
0x1800149f9  jns     short loc_180014A0C
0x1800149fb  lea     r8, aFailedToWriteI; "failed to write id attribute"
0x180014a02  mov     esi, 206h
0x180014a07  jmp     loc_18001579C
0x180014a0c  mov     rax, [r14+40h]
0x180014a10  add     rax, 4E0h
0x180014a16  mov     [rsp+78h+var_50], rax; unsigned __int64 *
0x180014a1b  mov     [rsp+78h+var_58], r15; struct _GUID *
0x180014a20  xor     r9d, r9d; unsigned __int16 *
0x180014a23  lea     rdx, ?Utf8OffsetAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014a2a  mov     rcx, r14; this
0x180014a2d  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014a32  mov     edi, eax
0x180014a34  test    eax, eax
0x180014a36  jns     short loc_180014A49
0x180014a38  lea     r8, aFailedToWriteO_0; "failed to write offset attribute"
0x180014a3f  mov     esi, 208h
0x180014a44  jmp     loc_18001579C
0x180014a49  mov     rax, [r14+40h]
0x180014a4d  add     rax, 4CCh
0x180014a53  mov     [rsp+78h+var_50], r15; unsigned __int64 *
0x180014a58  mov     [rsp+78h+var_58], rax; struct _GUID *
0x180014a5d  xor     r9d, r9d; unsigned __int16 *
0x180014a60  lea     rdx, ?Utf8GuidAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014a67  mov     rcx, r14; this
0x180014a6a  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014a6f  mov     edi, eax
0x180014a71  test    eax, eax
0x180014a73  jns     short loc_180014A86
0x180014a75  lea     r8, aFailedToWriteD; "failed to write disk id attribute"
0x180014a7c  mov     esi, 20Ah
0x180014a81  jmp     loc_18001579C
0x180014a86  mov     rcx, [r14+28h]
0x180014a8a  mov     rax, [rcx]
0x180014a8d  mov     edx, r13d
0x180014a90  mov     rax, [rax+30h]
0x180014a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a99  mov     edi, eax
0x180014a9b  test    eax, eax
0x180014a9d  jns     short loc_180014AB0
0x180014a9f  lea     r8, aFailedToEndOpe; "failed to end open element"
0x180014aa6  mov     esi, 20Bh
0x180014aab  jmp     loc_18001579C
0x180014ab0  mov     rcx, r14; this
0x180014ab3  call    ?WriteEOLWithIndent@ReAgentXMLParser@@IEAAJXZ; ReAgentXMLParser::WriteEOLWithIndent(void)
0x180014ab8  mov     edi, eax
0x180014aba  test    eax, eax
0x180014abc  jns     short loc_180014ACF
0x180014abe  lea     r8, aFailedToWriteE_0; "failed to write EOL"
0x180014ac5  mov     esi, 20Ch
0x180014aca  jmp     loc_18001579C
0x180014acf  mov     rcx, [r14+28h]
0x180014ad3  mov     rax, [rcx]
0x180014ad6  lea     r8, ?Utf8ImageLocationTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; _LUTF8_STRING const ReAgentXMLParser::Utf8ImageLocationTag
0x180014add  xor     edx, edx
0x180014adf  mov     rax, [rax+28h]
0x180014ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae8  mov     edi, eax
0x180014aea  test    eax, eax
0x180014aec  jns     short loc_180014AFF
0x180014aee  lea     r8, aFailedToBeginO_1; "failed to begin open element"
0x180014af5  mov     esi, 211h
0x180014afa  jmp     loc_18001579C
0x180014aff  mov     r9, [r14+40h]
0x180014b03  add     r9, 744h; unsigned __int16 *
0x180014b0a  mov     [rsp+78h+var_50], r15; unsigned __int64 *
0x180014b0f  mov     [rsp+78h+var_58], r15; struct _GUID *
0x180014b14  mov     rdx, r12; struct _LUTF8_STRING *
0x180014b17  mov     rcx, r14; this
0x180014b1a  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014b1f  mov     edi, eax
0x180014b21  test    eax, eax
0x180014b23  jns     short loc_180014B36
0x180014b25  lea     r8, aFailedToWriteI_1; "failed to write image location attribut"...
0x180014b2c  mov     esi, 213h
0x180014b31  jmp     loc_18001579C
0x180014b36  mov     rax, [r14+40h]
0x180014b3a  mov     ecx, [rax+9A0h]
0x180014b40  mov     [rbp+var_38], rcx
0x180014b44  lea     rax, [rbp+var_38]
0x180014b48  mov     [rsp+78h+var_50], rax; unsigned __int64 *
0x180014b4d  mov     [rsp+78h+var_58], r15; struct _GUID *
0x180014b52  xor     r9d, r9d; unsigned __int16 *
0x180014b55  lea     rdx, ?Utf8IdAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014b5c  mov     rcx, r14; this
0x180014b5f  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014b64  mov     edi, eax
0x180014b66  test    eax, eax
0x180014b68  jns     short loc_180014B7B
0x180014b6a  lea     r8, aFailedToWriteI; "failed to write id attribute"
0x180014b71  mov     esi, 215h
0x180014b76  jmp     loc_18001579C
0x180014b7b  mov     rax, [r14+40h]
0x180014b7f  add     rax, 9B8h
0x180014b85  mov     [rsp+78h+var_50], rax; unsigned __int64 *
0x180014b8a  mov     [rsp+78h+var_58], r15; struct _GUID *
0x180014b8f  xor     r9d, r9d; unsigned __int16 *
0x180014b92  lea     rdx, ?Utf8OffsetAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014b99  mov     rcx, r14; this
0x180014b9c  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014ba1  mov     edi, eax
0x180014ba3  test    eax, eax
0x180014ba5  jns     short loc_180014BB8
0x180014ba7  lea     r8, aFailedToWriteO_0; "failed to write offset attribute"
0x180014bae  mov     esi, 217h
0x180014bb3  jmp     loc_18001579C
0x180014bb8  mov     rax, [r14+40h]
0x180014bbc  add     rax, 9A4h
0x180014bc2  mov     [rsp+78h+var_50], r15; unsigned __int64 *
0x180014bc7  mov     [rsp+78h+var_58], rax; struct _GUID *
0x180014bcc  xor     r9d, r9d; unsigned __int16 *
0x180014bcf  lea     rdx, ?Utf8GuidAttrTag@ReAgentXMLParser@@1U_LUTF8_STRING@@B; struct _LUTF8_STRING *
0x180014bd6  mov     rcx, r14; this
0x180014bd9  call    ?WriteAttribute@ReAgentXMLParser@@IEAAJPEBU_LUTF8_STRING@@0PEAGPEAU_GUID@@PEA_K@Z; ReAgentXMLParser::WriteAttribute(_LUTF8_STRING const *,_LUTF8_STRING const *,ushort *,_GUID *,unsigned __int64 *)
0x180014bde  mov     edi, eax
0x180014be0  test    eax, eax
0x180014be2  jns     short loc_180014BF5
0x180014be4  lea     r8, aFailedToWriteD; "failed to write disk id attribute"
0x180014beb  mov     esi, 219h
0x180014bf0  jmp     loc_18001579C
0x180014bf5  mov     rcx, [r14+28h]
0x180014bf9  mov     rax, [rcx]
0x180014bfc  mov     edx, r13d
0x180014bff  mov     rax, [rax+30h]
0x180014c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c08  mov     edi, eax
0x180014c0a  test    eax, eax
0x180014c0c  jns     short loc_180014C1F
0x180014c0e  lea     r8, aFailedToEndOpe; "failed to end open element"
0x180014c15  mov     esi, 21Ah
0x180014c1a  jmp     loc_18001579C
  ... truncated ...
```
