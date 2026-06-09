# CreateSubCAStore(void * *)

- ea: `0x180057d60`
- end: `0x180057f6b`
- name: `?CreateSubCAStore@@YAJPEAPEAX@Z`
- size: `523`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180057a04`

## callees

- `0x1800110fc`
- `0x180057d60`
- `0x180057f74`
- `0x180058224`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180057f58`
- `CRYPT32!CertCloseStore` at `0x180057f58`
- `CRYPT32!CertOpenStore` at `0x180057d88`
- `CRYPT32!CertOpenStore` at `0x180057d88`

## string_xrefs

- `0x180057e89`: `MIIG5TCCBM2gAwIBAgITMwAAAD8gdFm/WNWTMwAAAAAAPzANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpTWljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTkzNjE0WhcNMzUxMjEzMTk0NjE0WjBbMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDEyNNaWNyb3NvZnQgVXBkYXRlIFNJSCBTaWduaW5nIENBIDMuMTCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBAJPUup61/vy6JITc5ZptPL4ijltCZFOcWsyVTNfX`
- `0x180057eb7`: `MIIG6jCCBNKgAwIBAgITMwAAAD4t0wm5AC9vqQAAAAAAPjANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpTWljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTkyMDM2WhcNMzUxMjEzMTkzMDM2WjBgMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMTEwLwYDVQQDEyhNaWNyb3NvZnQgVXBkYXRlIE1ldGFkYXRhIFNpZ25pbmcgQ0EgMy4xMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEA551QfVQDYBwt4nC60OVe1QbQnjfhVUVE`
- `0x180057f34`: `CreateSubCAStore failed`
- `0x180057f20`: `MIID8DCCA3agAwIBAgITMwAAAAtRyJHkwl0ZWwAAAAAACzAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA1UEAxM1TWljcm9zb2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMjUwNTE0MTgzMTMzWhcNMzUwNTE0MTg0MTMzWjBfMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMTAwLgYDVQQDEydNaWNyb3NvZnQgRUNDIFVwZGF0ZSBTSUggU2lnbmluZyBDQSAzLjIwdjAQBgcqhkjOPQIBBgUrgQQAIgNiAATz6OgXOBOqg5XWtX4wd7A43OONj6yID45N`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateSubCAStore(void **a1)
{
  int SubCAContext; // ebx

  *a1 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0x2000u, 0);
  SubCAContext = CreateSubCAContext(
                   L"MIIEaDCCA+6gAwIBAgITMwAAAAUaOuZqnuT4lwAAAAAABTAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc"
                    "2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA1UEAxM1TWljcm9zb"
                    "2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMTgwOTI4MjEzNDIwWhcNMzMwOTI4MjE0N"
                    "DIwWjCBgjELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc"
                    "29mdCBDb3Jwb3JhdGlvbjEsMCoGA1UEAxMjTWljcm9zb2Z0IEVDQyBVcGRhdGUgU2lnbmluZyBDQSAyLjEwdjAQBgcqhkjOPQIBB"
                    "gUrgQQAIgNiAATTEQTfeopESXL/n9i2PL6lYKUirRtn27mEarFs1/7il2YYnD3XrFFbv392nqQANw72jWIuyE0inOH27meYdBQck"
                    "dutDy4ubOVFnTJaIaFNDKHnwVcjaTmDdCblyLV2eQqjggIQMIICDDAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwH"
                    "QYDVR0OBBYEFNJGUVOkn2Mk8ujSsquFTJ4y/9hSMFUGA1UdIAROMEwwSgYEVR0gADBCMEAGCCsGAQUFBwIBFjRodHRwOi8vd3d3L"
                    "m1pY3Jvc29mdC5jb20vcGtpb3BzL0RvY3MvUmVwb3NpdG9yeS5odG0AMB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBM"
                    "BkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUQ+9wh7idv+yIGdzGxGt1DXU0M"
                    "wgwegYDVR0fBHMwcTBvoG2ga4ZpaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jcmwvTWljcm9zb2Z0JTIwRUNDJTIwU"
                    "HJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3JsMIGHBggrBgEFBQcBAQR7MHkwdwYIKwYBB"
                    "QUHMAKGa2h0dHA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2lvcHMvY2VydHMvTWljcm9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb"
                    "3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3J0MAoGCCqGSM49BAMDA2gAMGUCMQC3k681wr3A4RNQT6NhAVhv2"
                    "cxq89kmbGNtDILDz/NzFDWKs3A0/PiYNymenZsWxdQCMF4D76Biy22dGwUAnA5kzi8fEI1PXHDDWO2ygbsPqO9w3a85QKssXScxvldmA3MQpg==",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  SubCAContext = CreateSubCAContext(
                   L"MIIEaDCCA+6gAwIBAgITMwAAAAbeoIf7goRbkAAAAAAABjAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc"
                    "2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA1UEAxM1TWljcm9zb"
                    "2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMTgwOTI4MjEzNDIwWhcNMzMwOTI4MjE0N"
                    "DIwWjCBgjELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc"
                    "29mdCBDb3Jwb3JhdGlvbjEsMCoGA1UEAxMjTWljcm9zb2Z0IEVDQyBVcGRhdGUgU2lnbmluZyBDQSAyLjIwdjAQBgcqhkjOPQIBB"
                    "gUrgQQAIgNiAASv0GjjmOg/iw7gqNQWRSdg7y3xFuhfBgJpn5PZKVLhnBEEfXGEcpzJXuTWTs/hMKHuR4TDMaP8nY8NOUE4XpmGE"
                    "PwlAjuwAdnd0c7njUZlObraojiIK4qAFIP0kmYeYpWjggIQMIICDDAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwH"
                    "QYDVR0OBBYEFAR43gq59cGeqnyJDAKlDZ91RqdvMFUGA1UdIAROMEwwSgYEVR0gADBCMEAGCCsGAQUFBwIBFjRodHRwOi8vd3d3L"
                    "m1pY3Jvc29mdC5jb20vcGtpb3BzL0RvY3MvUmVwb3NpdG9yeS5odG0AMB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBM"
                    "BkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUQ+9wh7idv+yIGdzGxGt1DXU0M"
                    "wgwegYDVR0fBHMwcTBvoG2ga4ZpaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jcmwvTWljcm9zb2Z0JTIwRUNDJTIwU"
                    "HJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3JsMIGHBggrBgEFBQcBAQR7MHkwdwYIKwYBB"
                    "QUHMAKGa2h0dHA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2lvcHMvY2VydHMvTWljcm9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb"
                    "3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3J0MAoGCCqGSM49BAMDA2gAMGUCMAmSHIsxVTQi+LQX+K7kuDeTa"
                    "gTgdjmNBcykOA2Xoy9m1wXmQinLaNu/4UV6n90+uwIxAO3bnqKbucKDjaWNGX77Fou3mLzqMnf6WpOzIAoh7QjSMBaR0gR6qG/cWudLAVJIsw==",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  SubCAContext = CreateSubCAContext(
                   L"MIIEaTCCA+6gAwIBAgITMwAAAAfoFBuLBbX7owAAAAAABzAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc"
                    "2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA1UEAxM1TWljcm9zb"
                    "2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMTgwOTI4MjEzNDIwWhcNMzMwOTI4MjE0N"
                    "DIwWjCBgjELMAkGA1UEBhMCVVMxEzARBgNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc"
                    "29mdCBDb3Jwb3JhdGlvbjEsMCoGA1UEAxMjTWljcm9zb2Z0IEVDQyBVcGRhdGUgU2lnbmluZyBDQSAyLjMwdjAQBgcqhkjOPQIBB"
                    "gUrgQQAIgNiAATXNWgBKBhA9VwFKj7SHUV5N/R13ByyQDiekb2mfUZoFXGlHSjMdf5XKDkLphnM0L2aqRWdBXm6wERo/BwH5JHi/"
                    "h0Ia3JdSQwBd7i3T0RfRa8QGINHRPPwBgcilIzyi1CjggIQMIICDDAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwH"
                    "QYDVR0OBBYEFJrC9a4rIe9sI57t2+q4S02lINwNMFUGA1UdIAROMEwwSgYEVR0gADBCMEAGCCsGAQUFBwIBFjRodHRwOi8vd3d3L"
                    "m1pY3Jvc29mdC5jb20vcGtpb3BzL0RvY3MvUmVwb3NpdG9yeS5odG0AMB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBM"
                    "BkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUQ+9wh7idv+yIGdzGxGt1DXU0M"
                    "wgwegYDVR0fBHMwcTBvoG2ga4ZpaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jcmwvTWljcm9zb2Z0JTIwRUNDJTIwU"
                    "HJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3JsMIGHBggrBgEFBQcBAQR7MHkwdwYIKwYBB"
                    "QUHMAKGa2h0dHA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2lvcHMvY2VydHMvTWljcm9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb"
                    "3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3J0MAoGCCqGSM49BAMDA2kAMGYCMQDzG5/gag/H0EamWHnY4O86v"
                    "afMb4ZU9OujKkXfBI0RJStImOg0DV3xj8Kwfs6pO8wCMQDBa7pnVGYhiFlpHZtNEoSOW7wfTyk/fW9BdRQDg+lMGHQK0QauEEmy+cRuM6llACQ=",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  SubCAContext = CreateSubCAContext(
                   L"MIIHBTCCBO2gAwIBAgITMwAAAAexzEAnVUg/aQAAAAAABzANBgkqhkiG9w0BAQsFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAgTC"
                    "ldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpTWljc"
                    "m9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMTIwNjE5MjI1MzQ3WhcNMjcwNjE5MjMwMzQ3WjB+MQswC"
                    "QYDVQQGEwJVUzETMBEGA1UECBMKV2FzaGluZ3RvbjEQMA4GA1UEBxMHUmVkbW9uZDEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvc"
                    "mF0aW9uMSgwJgYDVQQDEx9NaWNyb3NvZnQgVXBkYXRlIFNpZ25pbmcgQ0EgMi4xMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICC"
                    "gKCAgEAvaBCirZW8HrAK1Hhyt3XtpfKAumdEhXO5jqSlz/u/jhdU+MkCX9wURt7xQ5czMH5kzUkSmEFPLLyLv/JXsZqyGJ4eUcCN"
                    "ak2RV1w/xStlKNJUBDCsxiADf6RrwRcooSvi+Szp0i96Lp64q41SQgZnGOuw8Gp8QG7wHuHO/wTEkohbyuav/Et6cuq/q7ai+LSH"
                    "dmTOxiGQiuzS0yNL7Tz7ltzL4pMqe/UQdOi4vVaMVWndkFRKb/9huv+epIaY1f1FSMVOT18s8rnJqHNZnkCMj9ff+ZN9A/n8rbLs"
                    "bzpEtxFArZlVfdsYF0YTSjpiug6i3GqtlX+33Ns1SHJuFBoBcPkCcm9UclfbXVPjTUwxYzBg7Ifk7Vyb9JEkB3tfxOpfVMknKpGw"
                    "I/Fxb6/yFUU/oc1/s3VfgLSh2gAybjXRMtx26SLs+AOpgvOEn32aNzAkTH4WSws9dXRLgidKzBqbqqtnhZOJ9C6OxqBMEM4kofhb"
                    "G9DPS1OHw0Qwfj6vITIk8OeR/y2+tEvtq85Ppw/HPFNpBbTCuLnTvU3iANGjh7Md8FH00S35DUj2+sgyyr1V64uADtr5qNuBZlwu"
                    "3Y72Dy0dvYoFTol1CakCJ/ZfntEircVisbFeCqdMsSDe7luQhSZXUl/RZlXpzN3RBr/R6Nxt7CxVoqO+lTfdBSjPakCAwEAAaOCA"
                    "W8wggFrMBAGCSsGAQQBgjcVAQQDAgEAMB0GA1UdDgQWBBStlHaPg60OA6PoO7DXNGjUeTp93DAZBgkrBgEEAYI3FAIEDB4KAFMAd"
                    "QBiAEMAQTALBgNVHQ8EBAMCAYYwEgYDVR0TAQH/BAgwBgEB/wIBADAfBgNVHSMEGDAWgBRyLToCMZBDuRQFTuHqp8cx0SOJNDBaB"
                    "gNVHR8EUzBRME+gTaBLhklodHRwOi8vY3JsLm1pY3Jvc29mdC5jb20vcGtpL2NybC9wcm9kdWN0cy9NaWNSb29DZXJBdXQyMDExX"
                    "zIwMTFfMDNfMjIuY3JsMF4GCCsGAQUFBwEBBFIwUDBOBggrBgEFBQcwAoZCaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraS9jZ"
                    "XJ0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3J0MB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBMA0GCSqGS"
                    "Ib3DQEBCwUAA4ICAQCMuWE4qgVou9PlXt/+MqVT42T5ni8T9qzL+QdRtvVUediPnL+p9rFDmnI8oyarrIN+8dg71bUP5Oz91/wVk"
                    "prim9jgcMdro83uzZo4lU0mNXVQj/afGEWt+2cA+TGiGlDRTtpWg2QRm0wdDdTQN8v8oVxYOoZZ5WMMqOY36VLAUR+Mk234MWV32"
                    "YGUQeCxDXzVMHydaiAz3tFsCk27sP38MtBULzrQN3gMFJf3JkHVrCrYGR28/4SU1BY2yQLJCPvHakhLxVq28dad/Gmc4mse/tTo0"
                    "SdFIxfbhoMYI8uSJbZEDjsjT4UugjirLwBK9SjsFDdkldTzSHejlMbd9ToXYM15LKaTrwwN2E+hfMcrUpYJtbHzCn35D8dezb+06"
                    "6dRVDRKYV6AC7cn5JblDww2WpNl0ZW2y3I9QO7BwfcO6x9V3+XwOZadZO4jKCxZbctiuxiwZVnO3lrjm9IcSD5VSJJxc1+O6dooy"
                    "hBGFZk/1m+45bxD+zgT1OOg78OT9LTVuqDMznZVbAQhBBdCvyP+tCO0A0hcetAXHjR+Y90rwT5buo0Icq10V1sovmRAXUcHInO9o"
                    "kECNX9lbsBf7hAWbGY+McHQeil0mz6ABN/U3m8Vh3m9AWhWe0SEU0fpJ29JxhaiP7/KoGfhScGEgn664wHrkmpZZQOnrhnvGCABPw==",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  SubCAContext = CreateSubCAContext(
                   L"MIIHBTCCBO2gAwIBAgITMwAAAAhZ45TgVMcXXQAAAAAACDANBgkqhkiG9w0BAQsFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAgTC"
                    "ldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpTWljc"
                    "m9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMTIwNjE5MjI1MzU2WhcNMjcwNjE5MjMwMzU2WjB+MQswC"
                    "QYDVQQGEwJVUzETMBEGA1UECBMKV2FzaGluZ3RvbjEQMA4GA1UEBxMHUmVkbW9uZDEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvc"
                    "mF0aW9uMSgwJgYDVQQDEx9NaWNyb3NvZnQgVXBkYXRlIFNpZ25pbmcgQ0EgMi4yMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICC"
                    "gKCAgEArgI6TDEMVbec3VCXnVOp87hJy7hcnR8wwGWIGm5Fvn7fyDcpsPJb3pPK4waQ3elQN8WEJUxUeNmm+jEK8m3HA2cjFSDOi"
                    "MSCHIEz2tKd0p+DIz5ZvQYqvHcFUt2lVsPHjuHVKsNYpAMhIXLgyDR2rbKo3V7XIxcO43/OtRUCJYqq6LCgdPbDGuaVXK/03vsou"
                    "RYRtEVNlSABIVJe4qNppiYvb/7+fthZdXoB6cDf8ThAF/gyUkGPmayIneT6o9u10BL1SfQezRVpc/kYZWUifRH3B2nxgrDn5n4OS"
                    "JJbAmKzLkEQwSDXFYfP83kbFhMcS5P/M+KkvlLhW8G7XQ35JuUI5KM3Y5ObR/LUkfZA7und41Y24ELvp2ndtcjC5s8LJ4XHYXGPs"
                    "u/RK/CPgvWKwC9M2x1uUq2WFr5eookUKn4OuqMycBE8h1pSdPf2nvBzA+nxhi/1JpOtgLOxj0+HemOK29fasS4CxCfxMMdtvXuYc"
                    "AL7fi1NCPWhDyWk1UA0ctFmNxya2GE8H8yKKWaYbAnxLDWqOnDolz/P3cstBmQyvsShWL+LKsw/2r+oOcKxMO1L3/ZWx2NOUuAgX"
                    "vu/V5aIzbHrvWfKP6IlREveslI5Q1b82b/0/F1k4lv9LBFSug5yZgh1KQkO0KRoKu+XqR5yPZXm1UyGN8KmopIk5SsCAwEAAaOCA"
                    "W8wggFrMBAGCSsGAQQBgjcVAQQDAgEAMB0GA1UdDgQWBBRdXWv7SyFKSLraZ1K5ajuNxJFVrTAZBgkrBgEEAYI3FAIEDB4KAFMAd"
                    "QBiAEMAQTALBgNVHQ8EBAMCAYYwEgYDVR0TAQH/BAgwBgEB/wIBADAfBgNVHSMEGDAWgBRyLToCMZBDuRQFTuHqp8cx0SOJNDBaB"
                    "gNVHR8EUzBRME+gTaBLhklodHRwOi8vY3JsLm1pY3Jvc29mdC5jb20vcGtpL2NybC9wcm9kdWN0cy9NaWNSb29DZXJBdXQyMDExX"
                    "zIwMTFfMDNfMjIuY3JsMF4GCCsGAQUFBwEBBFIwUDBOBggrBgEFBQcwAoZCaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraS9jZ"
                    "XJ0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3J0MB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBMA0GCSqGS"
                    "Ib3DQEBCwUAA4ICAQCl+LdTRbpWg7fXpE2oFlw5ks2NJbTm62tx5+Ba+eLRq/2xQ+UoD/7Ckbwn9AArdKwojtjGjZZzB6TjHhnW/"
                    "LWLoebPW1VNpRNHwa5H7/FxQUeV1fRqYBuT5+5qIA+djmi4T9n8NnyNT/Hlfd9wqhIBUS+Ljna6ZrmQgCWPd7T7wsQSlVSFiPLZO"
                    "MVlPlOeEdSiuNyIeQkXqVY18W8nAMo8RtOatX/DgkMQ8exKC1deApL+tD+tCzCZyfUg+hDV2ofMPp8W6EK7wRKCLmrOrVhSPnWdg"
                    "3SNvbMIHjMyuvSPz5H8idsBaetTzXPXLOKmtRQ0nicddvVXY2xZ5b8hT5ED5Xu057FHpiqdmiax0XwlaF3HzKn9kZJpz1ThuCfWM"
                    "s9gCxfaLnSWrE3TFJ7ZeQ/sI9bM/Sujz0S7yIepnc1PdW0WUlnO++GORk2e6udkAXB3C35QjhWBN5GHNQNEfpyUW9hVcaUweg3E5"
                    "GtpETEyTsDsE7lFp/4L1a80VSWg1YL7of2yUn9W7P+7ou0F3VYC4s0N5W8iabzVF+V9KNeN+2WOnSogrgqDO/sG277WiMqijJmv9"
                    "1FkvPSpfW7qo+e72+lwsZEOUl5ZjPcQ1lasky0U+IaEa6xTh8IAtURDkgFVr/HIl75KA57/PddgNwxd017SSSzweFrWbN+RP3XtOg==",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  SubCAContext = CreateSubCAContext(
                   L"MIIHBTCCBO2gAwIBAgITMwAAAAlShUmtVdQnFQAAAAAACTANBgkqhkiG9w0BAQsFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAgTC"
                    "ldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpTWljc"
                    "m9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMTIwNjE5MjI1NDE3WhcNMjcwNjE5MjMwNDE3WjB+MQswC"
                    "QYDVQQGEwJVUzETMBEGA1UECBMKV2FzaGluZ3RvbjEQMA4GA1UEBxMHUmVkbW9uZDEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvc"
                    "mF0aW9uMSgwJgYDVQQDEx9NaWNyb3NvZnQgVXBkYXRlIFNpZ25pbmcgQ0EgMi4zMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICC"
                    "gKCAgEArDmAyzRQyiY/XXYmytOMwR1c6zCXxmaGJqbVXV9PzYBMD2fsJQy7ORE7bob9xyEnYPyAfAGJrehuzb3QR19YbQA7RleZf"
                    "RazdhKLyp2GbB1wmmnURf7OcurKypRgnXxzsqFa7Xw4+PJi/3wnKtoLzagx05Qa9G+ipfXnJ93m862nrrdHrZD0OMCn8VIdIKqPa"
                    "OAMFSARVSwPZ+t++XLsuyJE3YtsPIDc3q0o1issGqIbLdpjTKVmZlMc6ZsNjUwTD257nfOHBmyKP0A5ck2phFwzRJ3d6YduuC+8F"
                    "O9FV6diheeqo+yNUU8zXN22AvzqCzsGW7mrHtrJuOpB92IyLk0QXOahGVVtfco4qBJf92F1IBFjHSh4Fo3hbQ1bq8xQg4VGR2Mf1"
                    "b+VLSchQ4rFfNjGbXUEZNOWK/2pqJkftxIpF4mD876YcX+B2FRMsEIfG462NjMeL4sQMdkTPE3lpFGIrSiYJWNpFDo+0k4N0QVpk"
                    "pZ/j1dbNlaZfrWrmRPlKQAAVtGbZtrmzp6H5xKKwL51WUFxhxrRSl5d8dqHvxtanD01ufjDUJ7gYnw4BMMiD79jI9tB8hjy88TS1"
                    "Xgzv+6ee0ZlYp4EegEAWpryfTaCmIyJgaIufrVt/XpSghAE/PeJq1PeRmkUte2Se0534Gp/wb3Uxhg97W22fp3K49UCAwEAAaOCA"
                    "W8wggFrMBAGCSsGAQQBgjcVAQQDAgEAMB0GA1UdDgQWBBTQ8/pf9Ub1y7PYj66PjOyGHN9hyDAZBgkrBgEEAYI3FAIEDB4KAFMAd"
                    "QBiAEMAQTALBgNVHQ8EBAMCAYYwEgYDVR0TAQH/BAgwBgEB/wIBADAfBgNVHSMEGDAWgBRyLToCMZBDuRQFTuHqp8cx0SOJNDBaB"
                    "gNVHR8EUzBRME+gTaBLhklodHRwOi8vY3JsLm1pY3Jvc29mdC5jb20vcGtpL2NybC9wcm9kdWN0cy9NaWNSb29DZXJBdXQyMDExX"
                    "zIwMTFfMDNfMjIuY3JsMF4GCCsGAQUFBwEBBFIwUDBOBggrBgEFBQcwAoZCaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraS9jZ"
                    "XJ0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3J0MB8GA1UdJQQYMBYGCCsGAQUFBwMDBgorBgEEAYI3TAYBMA0GCSqGS"
                    "Ib3DQEBCwUAA4ICAQALk1sBJInA3QIQYC7QNAFVDfDLUqsUcOZS4Ty7G4exgQ0XyN+BNSluFM3TX9zovQqDKkm6+HxhbIK3HmAmM"
                    "qOwWGBbgAAoC1g6lp93sF/rlJWRjrTUoesgSZvE9YkxdWf1F497li2ONIrVp87+DSSPfDPax02FgG1d9knvMfa9D04Ht8fLEbrLe"
                    "tnZW89xYxpq9FmratQGqcWDkTIz3K9lmr1YonYuuG7/i1XZfcHTjb1Ef4HbeNL75GdXOpeI5BIYShzvhzeCy5D5fm+qCgA9z50Md"
                    "nC6cOi6zNIqUvSN+5uyyLF3RD8X7rLJtZ/AF8t+twdmLEk5g3UiokknYazEeMnc3uOGvUzs8oFP7sMCjAOPYv/EPOkgr2tvAGVHA"
                    "Gbqk68ZrBcDrp+QYFuHTQ4crc2GVMVjSW4AYy+vpaWumrMSMjB7/Kl+8avObp8GBdCpw3/KhjhBYq3tTGO4RWsZrLa4K6B5FAQbh"
                    "v8hkO7NjhPMu4fucXq+kjVabTiVeeKv5fjVzVAGxRtEiB/v8FasjOceWrdqCBjOiJDpDaAMGBEu0wWp3LkbG8NRZTgPqUTh9kCza"
                    "Wl/kH5UyfWOqrgPAKN93dWZoTFTj86LT+SZfeBvPE4k2LyXIFjsOgOvVb5ZW/+2AgZ4PG6wlitYVtmYvrimnxlokbGCClJeIQ9D6Q==",
                   a1);
  if ( SubCAContext < 0 )
    goto LABEL_19;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
  {
    SubCAContext = CreateSubCAContext(
                     L"MIIG5TCCBM2gAwIBAgITMwAAADxVlScdgs0HkwAAAAAAPDANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAg"
                      "TCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpT"
                      "Wljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTgzNzI5WhcNMzUxMjEzMTg0NzI5WjB"
                      "bMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDEyNNaWNyb3NvZnQgVXBkYXRlI"
                      "FNMUyBTaWduaW5nIENBIDMuMTCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBALAmzkN3ZfPBXLRs390Xv0fub53JXRw"
                      "6FWaASMOEmbvE9UxdTWRdyG/U+BScTdjxA4AvaDBoxUZpVFHHbF1J5a794S5amIo/3bBjhgFvgx9i3S9C5KvNXUsMSXLD/Q61d"
                      "7D20SPdADIdDLS2fwJ7s79SQ7rUZjlHHq07FkXyvMVFlw6Xzz07qcO5XIGz+x1E5CHhgz18t1Auyh0ETIoUnVuvVTDp5ybcXpA"
                      "QRSlTf/TV8PKPb0fGQRqWNe4Q6QJpdZ3GQ6+6TRveotwDnQdgxmhTyzqOuTjUWYpETOzBiyZGOMoYKKSjql0jcimEIXyTT//Vk"
                      "VeJxc9miKSzvn/aKbQpX73uNVOh7+BsQTQAwpfSu0dDmSDMlV2kqXwUvFc8wzxhVP0Xfg0g+0mvRiFJWSy6bEFth+EZqhOR2OT"
                      "WuqwCvYgeOgxmgWLAfRRJSwWm9Oquwo7ZZnldPP4Wc1DSmvFP1yL+R14U5WR8IoexR8G7QlWgn4zw4uibxfBfyg0PtZVYGkpI3"
                      "NCNf5eDbxh0n/p5s8ZNXcnkWJ1m8zyFtUg/MeRKlEOk9+B/9+ZRRScCyY9AHNUSuoWkQpu5Y/u+C8et7y62DTtARy0H8f62gyr"
                      "oyJjfcCkM9wLq3Y97tXIlCzDlsGnBzSqIIoQ34IBJ8Z2gcSK4UO7RkJpRPDXqvl/RAgMBAAGjggFyMIIBbjAOBgNVHQ8BAf8EB"
                      "AMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwHQYDVR0OBBYEFC74UOWecp2DCiwiB7kEmHjmZ7RhMCIGA1UdJQEB/wQYMBYGCCsGAQU"
                      "FBwMDBgorBgEEAYI3TAYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUc"
                      "i06AjGQQ7kUBU7h6qfHMdEjiTQwWgYDVR0fBFMwUTBPoE2gS4ZJaHR0cDovL2NybC5taWNyb3NvZnQuY29tL3BraS9jcmwvcHJ"
                      "vZHVjdHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNybDBeBggrBgEFBQcBAQRSMFAwTgYIKwYBBQUHMAKGQmh0dHA6L"
                      "y93d3cubWljcm9zb2Z0LmNvbS9wa2kvY2VydHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNydDANBgkqhkiG9w0BAQw"
                      "FAAOCAgEAQRwenbHDUCC1UHVgfmevxN9kWDGYMCec+WQSDEUOKDsdpAHk14FOrL/9ekGH+WV5tjw3h0HZ6hNQdbX/CYnUk7FgA"
                      "4niu3Q68ZLxg7DZCrR90kjj/BPEtBv13EP9L4ApqtHOUZmWB4oR2kLvVH/x0Ezc5Y9gmOhkzZomghFykYTic2QcGwymJNt3ZKP"
                      "+ivmtw2qSul1kcIBYMnSWe58R4qnTiTCkiLC2m9coOg0+Oqi7JY/pbuirXirpWaqD2fxAP5upwZKPpEr7DaboXrWWCYYTqlLz5"
                      "4b68KNqhnHZsdFVsR3ECS4/keiFRa1CXTWx5J+WWZMKPtQ7ycAZRdhTGiUUpPZT6BmVnS32EvyWiyTf0cBvuSAwhim/UoGhA0M"
                      "4YiFvum1/31+6NNjqWSQLGEtDARf69Ujib/kac5A4h/7eud+bGFwQv4Ruwt0nZLqNUAfjpmQ76jj7JBENpx4eTR/O1ThG8kB1f"
                      "Vo/U5tAkG2wa4y5j5+rP7VkTdt05lUDJI6O4mXd5vHGWniHjH1RapCxME9ly34kySggLl/i22NpNscZO6kGKHDlC4V0FYXuD73"
                      "Clyhfj2KkXTSsN+4P6/SOa5houCdOqwzkjwWL1PNoabdZs78NgUgfcMacFW560tl+7nKO+wJVf24uOK7+CjDiamxwkE8/ESpru2FmzvM=",
                     a1);
    if ( SubCAContext < 0 )
      goto LABEL_19;
    SubCAContext = CreateSubCAContext(
                     L"MIIG5TCCBM2gAwIBAgITMwAAAD2Go7M62EXyMAAAAAAAPTANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAg"
                      "TCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpT"
                      "Wljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTkwNDI3WhcNMzUxMjEzMTkxNDI3WjB"
                      "bMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDEyNNaWNyb3NvZnQgVXBkYXRlI"
                      "FNMUyBTaWduaW5nIENBIDMuMjCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBAKI9A5JI2WcElApALJUlnc8I2YTVu2l"
                      "lM8E76FdrkWz9vkErUSJAH4Pky0V6vY0uX5czUOkDKbshK55jeVxPPaPtswqWygkklHJWttuo45m7pbC7q47octfoW/vPEbLI6"
                      "aO2pRr4PkrkN+p3vySBiI8T0A8sYgDu+Bso7tp2Kz+8Heit8oOp/rDLIdaTwU5kKUw24Axl1lASUR171hFFJ1iPq8Q0kfAIW7x"
                      "oxcRPRKlQ8zSn2tmO5Uq6yAA0WtsfjLdRr2Drjixuh5tQ0gQJz6fBXlITZS/l6Vjswvi3NnP2uTZGygojHT9+8zp3ZonWKOn90"
                      "u+5B8jquOF5HDNbi4V7EAYsorjp1ZnVwfiVUYVScvYWfuFIi7GVgOQarXxCJuEy6uFHp/Nj+7u1Bln712K8wlITtuRXm5NJ1lY"
                      "MKXy+/AhL801HMXMyhECOUaZzB0Iek6kzDfMoPudjAsvIrrQksc4hAh+XjbuidB/E9i3DoiUjgU06D1IC73H/0vLtR0qgjHFwC"
                      "SdYQMgvUOP8Rs/kAPZHMlP+UnWwIgCt7qEudS/GEGadt7KnfTm98afYkO1R8Di9Lly/Q5f78vA9ARJPcXqJ6Geee8BPfF9XhHh"
                      "Padb78mFgYG6erhraZllbD+VXd7lwyXAicmUrZTGgs03VhEBxxWoVCNYmEB/AShgdAgMBAAGjggFyMIIBbjAOBgNVHQ8BAf8EB"
                      "AMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwHQYDVR0OBBYEFNX64KoyTN0d5DaLOUH3+Afi41EuMCIGA1UdJQEB/wQYMBYGCCsGAQU"
                      "FBwMDBgorBgEEAYI3TAYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUc"
                      "i06AjGQQ7kUBU7h6qfHMdEjiTQwWgYDVR0fBFMwUTBPoE2gS4ZJaHR0cDovL2NybC5taWNyb3NvZnQuY29tL3BraS9jcmwvcHJ"
                      "vZHVjdHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNybDBeBggrBgEFBQcBAQRSMFAwTgYIKwYBBQUHMAKGQmh0dHA6L"
                      "y93d3cubWljcm9zb2Z0LmNvbS9wa2kvY2VydHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNydDANBgkqhkiG9w0BAQw"
                      "FAAOCAgEAjVJykfkPSuHt9DI1X/xQbb8ThhFO2TfxyYiUmJoLV0I7uRpFIQZU+DU4Dz9oEWeIMLABTNH+oYcBmcUdznRDIQRqg"
                      "G6liAx7cPX4HXIBeWI8lJnpbgJeMOde3/3NoYJIfQp72+QMCVH67r7XcUHpcpeqItik0omOqjXGaTMnNISH2VYAYuA0OLr/LcY"
                      "yWWj8pcXWp4Lfhe0dhOyJAuixeb2ZHrNTfwSR2MLMd+hS50ipKLnB+HViNhkftgMfarQJeJ9sl1BlhIbXlIH3Bn1wnWJc+bV8K"
                      "5p2RBkWwWJ4Yj+7ZT1JRJ2cglUQYfHzUppkYp+xFnsn4w+hL4kVc5xFtTX7CYHTntvm2sxa1Mm2yzBe503rSCmp4MbyAxF1p19"
                      "LkWzBgFfZ7MmsyY+zNYyLNGTJFsuyypdZSTVbBHZNSkYS1MShuvEmaJvK7H9cF7bkE8Esq3G9Y8SDVOkWxqXBkV8LUyX3uxkv8"
                      "E1t6eD7JbTN9l70SlB7wmO66gSc2RCFXXYu8REB501zoNXzwnut5NWIYdD7eO7EP/BZxRJq2n1f3qbPPOcTg/KL09N0dQtdbWm"
                      "KVuP4Zn1FGUkXrlWjz2NRe5WnL2J10qmI1X9GSEK6HK3LELyBeXRXccgQZgaoDV/AGh7YbAS0Edp5383xej+H5VzV60gEShS59kRCEss=",
                     a1);
    if ( SubCAContext < 0 )
      goto LABEL_19;
    SubCAContext = CreateSubCAContext(
                     L"MIIG5TCCBM2gAwIBAgITMwAAAEA6aMvS/jxdFwAAAAAAQDANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAg"
                      "TCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpT"
                      "Wljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwNTE0MjA0NDA0WhcNMzUxMjE0MjA1NDA0WjB"
                      "bMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDEyNNaWNyb3NvZnQgVXBkYXRlI"
                      "FNMUyBTaWduaW5nIENBIDMuMzCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBALmJ97mICcfd6aPghlMp/0J1Bj/pv2n"
                      "09h7mE+tz1bp15UINef/FYhiYW/+nYfb+pWSlP1L4c4BMbZsrCJWSp5Zx58ZNXDsdU7seCGICHVfj3//JaZEIX+Pb1YLE2tpuf"
                      "8EtmYBWjQEGk6P82AdZu0vgjIWB79TQkIYnblKywwu9VukhMCJmbCt+eKPZYPLVE+vGtSEvfPFFyMMjAs1eC80sSEVjt8Uj9Ys"
                      "seFwrfPlgJnl3afEJ+iS3djshx/15kgyzhk/kH0Syb2iOhkVryPIV/c1qjrTEGn2fIuLN4mvVznap1kq52J8jAfru576LpELiE"
                      "n4LLye+9x34AKzXmJSMvMYXuj+WL9Rm5Rg0cfSM4nz7XiAZSJk7kvTRhsVusm4KrIYfyQnWTL8JR3YPDtf6qZVGxBXfyv5Xu6i"
                      "v3MjYSgxdhyddA7OCNP0HYCqPkNZo3IKeMd4SamRgRlTEZGyG8ZB18x9J3JQ+NGbN9fX7VIMKy5u18J+mQpU82q1Nq7TfAbiKY"
                      "QuRKvLNeZKeTyTpzU0cNlCfql7GwHdukd09jqm/rGX8AcZpp3X3fHwGqr3dq58A0KJEciJ4vru6NKEoCSEbzmcYfs4FnFTimBC"
                      "dCkz+B8XZKw8Jz2b5+ScV0dxzLvaPE265L4ZAXmjpZmFjmxFY+/wi+1m83tUOYhyNAgMBAAGjggFyMIIBbjAOBgNVHQ8BAf8EB"
                      "AMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwHQYDVR0OBBYEFNqwyAYGzka0PvrSdrx2jBLBvmklMCIGA1UdJQEB/wQYMBYGCCsGAQU"
                      "FBwMDBgorBgEEAYI3TAYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUc"
                      "i06AjGQQ7kUBU7h6qfHMdEjiTQwWgYDVR0fBFMwUTBPoE2gS4ZJaHR0cDovL2NybC5taWNyb3NvZnQuY29tL3BraS9jcmwvcHJ"
                      "vZHVjdHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNybDBeBggrBgEFBQcBAQRSMFAwTgYIKwYBBQUHMAKGQmh0dHA6L"
                      "y93d3cubWljcm9zb2Z0LmNvbS9wa2kvY2VydHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNydDANBgkqhkiG9w0BAQw"
                      "FAAOCAgEAMwUfQNgT0FcauBZLROBg2JPkcxKyYEPRJZfBz7d+vcGhnm37GGOEZgm/tdVpiODA885Xn0jIOpmW+OlmXsK2fju7Q"
                      "e0BwyFdsPOomzHXpInmR8O68fNp21HSxXGGhIuNzIB5jWbIr/SmvFTeLnvZrcaPc1amM8BYrs0tMVgcLyVmWrxG+KxfsluE9yQ"
                      "mbWIsdHd+WUD3iVEzgMMSu+8j9+tb5XuqDHo8Z3uAljc5axK5+xRTIic/BuAu9g2+DQWUz8oku/+8qvfSb91Y8nNmOMr9DNOuF"
                      "mq6nKfaL2DuMZh+DSCTtQaSjhDa/T1L8xU2r6KywZbSJ/W+4VQ9+ZQ9uAJ/ZpXjMyhcYv4Q9ToukNEGa1GwfgtCiTZYzdBre7H"
                      "KxTiryPtnVnAI8XjOnHuuYwdkJJe0f+Cl7dmTdcB3zBsHc3BayR9eqLWlUrhMecYThtkZ/r2TIssOZ23tSWS/W4JsMijXAHeDa"
                      "70h7uPC0heXDaI6w3cgonC310m3hzfHJW7wAsMfRGxVDTE2OyR3P+KR4oNqZ+4jPG1NtScmkI9Au++FR91igrmY/KGe18Bck47"
                      "8zZaNJxXVFULEAru1up8C1e+hNF6FJvvsH2vUmBogPo4cTovNHIPactps9tw4mdfCZqSZotWvfHdq6+g+al2bJRy7snHBEyK1+XtlsFg=",
                     a1);
    if ( SubCAContext < 0 )
      goto LABEL_19;
    SubCAContext = CreateSubCAContext(
                     L"MIIG5TCCBM2gAwIBAgITMwAAAD8gdFm/WNWTMwAAAAAAPzANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARBgNVBAg"
                      "TCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyMDAGA1UEAxMpT"
                      "Wljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTkzNjE0WhcNMzUxMjEzMTk0NjE0WjB"
                      "bMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDEyNNaWNyb3NvZnQgVXBkYXRlI"
                      "FNJSCBTaWduaW5nIENBIDMuMTCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBAJPUup61/vy6JITc5ZptPL4ijltCZFO"
                      "cWsyVTNfXpuRHMLylEMHqfd6xIpQvOdG2BWCyi7LMZcn9qZwSCL09gFk2iGy6ira5ITwt/Uy3U6vIeFRCTMfsjgGKcOKCJx8nK"
                      "tUJuCnjmMPpr8IY3/UGNDUhMZNDho5xEksZGQKJFgsbmMYVakg5E256vABpBZ4KdRXh4a6xEgb13Hq77rYzZ0meQww3hUCubY/"
                      "05Q9fQ+JNj1JPx54razdB4Lqj0JuBreYeD2pVvGBClJXyuH4SVCQSfarRV8GeuqpW18xoSAAEWjQukjnsqSwa3k30onLbacLsr"
                      "pJyqHZia38FovlunS/sdYNmqHY+werG0q6mTqS0sKDNmyCUG4iO8ffm6haU/g12hZoXoIZV5RI35ZbHcgTRR0ic0qvJI3bFkSu"
                      "NIibeXKhSb593v31xGu0QO9WRi3dyM4JnyzaMge+N6O+ljV1DA6z3oTinb7yp4pNu7y+3759DYh8qJmINv/85RdMMGuSEnbl18"
                      "2cl5jhL8g+MrlvKt+D9tpq88U8UsnTNedmYEXipGOCbJ4WiKn6UFH8RZDCgKatHJQ7mBxf/nTOlnKZWIMeslXd5bJMWm8tGtcb"
                      "t//qKk+kYkiW1rGL+01pydZTSuRWPwTzg9KVMQG3oTikBTiDOV+e9OlWa7VC2i5fJAgMBAAGjggFyMIIBbjAOBgNVHQ8BAf8EB"
                      "AMCAYYwEAYJKwYBBAGCNxUBBAMCAQAwHQYDVR0OBBYEFLR+BJcZ37938jXtu0V9dNmBiwYFMCIGA1UdJQEB/wQYMBYGCCsGAQU"
                      "FBwMDBgorBgEEAYI3TAYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUc"
                      "i06AjGQQ7kUBU7h6qfHMdEjiTQwWgYDVR0fBFMwUTBPoE2gS4ZJaHR0cDovL2NybC5taWNyb3NvZnQuY29tL3BraS9jcmwvcHJ"
                      "vZHVjdHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNybDBeBggrBgEFBQcBAQRSMFAwTgYIKwYBBQUHMAKGQmh0dHA6L"
                      "y93d3cubWljcm9zb2Z0LmNvbS9wa2kvY2VydHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNydDANBgkqhkiG9w0BAQw"
                      "FAAOCAgEAkMWRIcX1IZziaCfySFBvdfQSrLFH0nOqNI5zpC+8/HojGSujmOpZy+yWliX8UmaJvePSG7q7U6AF7urygRF2ouSoZ"
                      "WLpIX7D642Qn8vUEAsXDYiLOF6vAFG3wvNblAiFMEm90P3fc9MiCGEtpf/RngT+jkMqC9MeTGQqvZMtq5Ca9Ck6KH4wkMl8hw3"
                      "ati/KUhdYD8AO1n8+/4gmOW5y8IyNgQWjwUPM48yZNINg0hw4aRnJ9NDqyuu6HmpFGgER4FALq/n8eOLGOXJyXpuPLKTYP7rJO"
                      "I+OVaeMS1pI/piA97P6PEhwD1Dv3wPSzhQGOvxCnqnzRx/C3ub395HPynM8TJAemAgHDmbTbNFNsn+kNE+QVWyn2V5jEjx0+/h"
                      "iQXe6b3HuBVo56Z0u1SJHS+sPHqh8L6bs9WXAne+UDJ+ZOcG655cDWgZ2zksZ/IFkVgK+7qbBrJUU/uSkp48+77lg1Qgg0m6US"
                      "iasO8MO49+svjt+MR2Owk/ylk+7kOK6M3s/p1dKx3LHP6PlfvDILEQeKXXZZ2KYKUKq2YYON0Ob9FvMqp7TITgZslw4iME6sAs"
                      "o4FoJBxkLJw27u7qXFAtPxfAngnJVBhQgk5j8hvLGfT+k/6HAvGyBWCd21CHEcQLIkHUCQcSQmUoMqCh0TKGQItMjm/DSSyxGoiusOYU=",
                     a1);
    if ( SubCAContext < 0
      || (SubCAContext = CreateSubCAContext(
                           L"MIIG5TCCBM2gAwIBAgITMwAAAEN/oPFwfkwfdQAAAAAAQzANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARB"
                            "gNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyM"
                            "DAGA1UEAxMpTWljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwNTE0MjIwMDMzWhcNM"
                            "zUxMjE0MjIxMDMzWjBbMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMSwwKgYDVQQDE"
                            "yNNaWNyb3NvZnQgVXBkYXRlIFNJSCBTaWduaW5nIENBIDMuMjCCAiIwDQYJKoZIhvcNAQEBBQADggIPADCCAgoCggIBA"
                            "MiumikNqM+CR3EFsj4wVXLzUIY83+GwDuA9VXJk4b+TmLCuBghRuSTSGDH5/tI2hhRp2EA++VI0x4jQJvQLgALvpnhyH"
                            "3Cx1HVu646Us2GV9nqavM+xeO2aBIwnrFmlX4A80/tl/Eq+Z8a2ZtaeHhJNjBR53vTokZiXQI0vvos31wwjL/10pWl/G"
                            "jV9H7BV10VLX3on4y2FzPuF7X0Zd2LhMJUF9USmTJHasczsTPMJqM3DJy/BUmPmwNJKZwC80u6eusf9RpTDLNuEB/Pmm"
                            "ZNyIvgb8dUyTqJHTFgYf6fe3PfRCMbz42mFgp0ifzVdi0e9VtyfzgPWF3BkR5Ea0IumlrLa8TW2OtCl/1aazoS/mdKlT"
                            "f1Xrz3x4GB+fsQuhElwpVpxpHN8kWwyKg3fm8FKoOhlUy0ks+/8R2HCDSR31ViS0mib4wW8I4peZ6Z6SpAgIt58MDwbw"
                            "/GdkqfpyzhSeXZwIm3bBXXdAwYGy6ULNglc7RcosNuf5KzYqyy8gh9Dh4/RYY4rgmJz99R/4m3MUGNz1agb2ORmx4FCa"
                            "XBsJMSw+fivu9vkHyYnNidJssKdYSaPoHQ3X3erMhtuYu/sb/A4AAZQpJUy++d+uhCW71Djt2QicWGuc61btz5OvH5LV"
                            "B83uvfBnTKWEGVLyW2/QEUo8uF9P5Tq6hTXKvJTAgMBAAGjggFyMIIBbjAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCN"
                            "xUBBAMCAQAwHQYDVR0OBBYEFLRC2WDfRwbocCpzvUGaYYMKfH0DMCIGA1UdJQEB/wQYMBYGCCsGAQUFBwMDBgorBgEEA"
                            "YI3TAYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUci06AjGQQ"
                            "7kUBU7h6qfHMdEjiTQwWgYDVR0fBFMwUTBPoE2gS4ZJaHR0cDovL2NybC5taWNyb3NvZnQuY29tL3BraS9jcmwvcHJvZ"
                            "HVjdHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNybDBeBggrBgEFBQcBAQRSMFAwTgYIKwYBBQUHMAKGQmh0d"
                            "HA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2kvY2VydHMvTWljUm9vQ2VyQXV0MjAxMV8yMDExXzAzXzIyLmNydDANBgkqh"
                            "kiG9w0BAQwFAAOCAgEAmz05XB1xmEUu7Ippn9rO7frnRKGUiXiVIasuMysXcrFrIPoeGG/9xCJcQQLmYzyeV1BuAuGHK"
                            "lMOfvG5OJomn9eHnzFPSMGio7pPJKPBL1o8gl6pbMzGuvIIIWUHb8y1XaOP5a8kQgZq7HSqes9UHUkSO0T/+BaOr1sXz"
                            "W75ivnXL5VxyeApkosXZT2sBvAPykt97mTT3IrpS6NsDwGkFVh1vy5mWAjyIbCNIoXyzm+TVZ3Yl6nDXav6aeR7VlhSU"
                            "cH7rZVVgOOTDiNVRrUl+JlxkdD6aSDdKlkLxOKn0+xk4oFh788x9GsDyP0NJ+CBP6h84pGZS2In6LKgXycOC6I9rSryq"
                            "R5LhnjxMIkzbWFH6fM0o7XWjkHBah/kWpbgcV5u17H7EPEnuZhiLoqUo+TUd81kIko7417ib2TISzxSbLIGALlb1Tsk5"
                            "8qiB9iN1zuke4QK6MY2vhT4TrqZd4cQiOsfjaaB5Aj2Rg20zbeRhjB/AGEeAjixjOj0Asf0Dpt7TxFvRjNv02U5kTtAC"
                            "9AyajNM86VSStgnV+/LWqdcp0XwHkH4EtmPbEqAzUFKHJHJX/WLzyMsENEQO1XV7+mnPm/6Vq9xfmr/BLT5RLWgZ/KRh"
                            "Z5ed6HviodrfCHBdY7SCuRR7HbRDx0M4yPHSaHRbR8GT8wugB8ZHueqf6E=",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIIG6jCCBNKgAwIBAgITMwAAAD4t0wm5AC9vqQAAAAAAPjANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARB"
                            "gNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyM"
                            "DAGA1UEAxMpTWljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwMzEzMTkyMDM2WhcNM"
                            "zUxMjEzMTkzMDM2WjBgMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMTEwLwYDVQQDE"
                            "yhNaWNyb3NvZnQgVXBkYXRlIE1ldGFkYXRhIFNpZ25pbmcgQ0EgMy4xMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICC"
                            "gKCAgEA551QfVQDYBwt4nC60OVe1QbQnjfhVUVE4U6IlbugxPmKEskL3Hol4WAxTmpoqBV881rEoy+LOdgsX4k7fSn7V"
                            "dxnqFPNtB+Iw2scrlySmaThuaXlRf6r72/39Bsi9vzA6zdmr7CUhydvmHTaJFf8bCJvCu06e2kFh/2g15UyrT2pSne2b"
                            "c5jXhJQ23Z8wp9Ve7reubyTyEKPSQxGS0uvMuc+78kiRMS76eVHyC32zIUqloHKuyXqFXoaPIseTqH1tZ0gnWtbDp3Hk"
                            "sGhILftaEsRmyO8pL9nJj7UOcSWWYzr//9930TFkmcjBc7vPz5AtxMlEW4YBcg4ouvGZqFhiIlTZ+YEQtsebqa1ZPtjF"
                            "2q1ciifbVC8JZgOxbhG5WA0EHgF6Q3yLNzhWo7DIBAzK/ccJTiwnyJpFPJW07dP5qwuUIFzuldHojL4TU1F+VskVlVoY"
                            "be/lUwTdYgPCupwkKXX0edSFrvCagUPt40M7SeD5/Q/xMnCW4/YwEX0YJ82d+i+1i/oY46p2ENftFsKOdXZQ/RKsJVJF"
                            "S1WMC1z8hrG3ySCH6RrfwaPp+pNp9ODEl12AMCl1chnyrfQtpnPChz6LIe+L8udmo1EeDBmHHvP2hFJykiQMYgNJs3EZ"
                            "Dy/5+9DinYBhHpJFaSIEeinyOG3FTGdV7oljfbpCHGTpdMCAwEAAaOCAXIwggFuMA4GA1UdDwEB/wQEAwIBhjAQBgkrB"
                            "gEEAYI3FQEEAwIBADAdBgNVHQ4EFgQUuptbx7atpwQJDCajltGnGIlPkDowIgYDVR0lAQH/BBgwFgYIKwYBBQUHAwMGC"
                            "isGAQQBgjdMBgEwGQYJKwYBBAGCNxQCBAweCgBTAHUAYgBDAEEwDwYDVR0TAQH/BAUwAwEB/zAfBgNVHSMEGDAWgBRyL"
                            "ToCMZBDuRQFTuHqp8cx0SOJNDBaBgNVHR8EUzBRME+gTaBLhklodHRwOi8vY3JsLm1pY3Jvc29mdC5jb20vcGtpL2Nyb"
                            "C9wcm9kdWN0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3JsMF4GCCsGAQUFBwEBBFIwUDBOBggrBgEFBQcwA"
                            "oZCaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraS9jZXJ0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3J0M"
                            "A0GCSqGSIb3DQEBDAUAA4ICAQApQ4nWqnriKberr8KDnnLESynq+3WPpaN05vdWsPkN1Iihgo5N9NXOvXunCfrqGzqse"
                            "Y+7SN72Jk1tt8woyuW79UPj01Vbd8M39wWphjYTTxlzw94BMOZjjssE8b0nJ+krgRxHShEMmt9U6LF61GaHuwqNJckZU"
                            "mGt4UQF2Egyp1+WMowm2frXJIfChUQ1Aa/884wWqBD34602a+Rd3KqQknHhglDoSe+0aNShc4NKQNDdR32gXefj6uCCa"
                            "c1iJ0xYdJCOMvNaMyGUBt/awmwsaXvr07NwqDPtrfwAafENlIX6013t7Am/7yP62yLdA2aDOB1g6LkgA6Fhpd0vXk4wP"
                            "SlD28AEF4WAlr0wxEFjHUtGQVxhMypbm2OzyM+CzZSexYIl800tzekG7ngQ+cXqg75TjprlI0RnlN0sPr/2PkV4c+YD8"
                            "Rca1J3Kzw0pcWGkey8zkpQ4etSY7Sf+aKxkmERQmYVtkJ7K+Ps3oC8y2Jhrp7fNIkcqiCgUT3mg1C0vE+XCMNQFAgYGm"
                            "NIOFT9RErbuTXIVLK+hWO/W7YYVL1RK9S68+JjTA/pc+rVHEgaPH3pkcogY8fDZBERE78vPTub1d4cf10eJLycs1HOaa"
                            "kfIffqpU4ztroSbD8jSE1Pqg5965Ia++IPV8jdz/miuCJHio8mdY17Uoy11YMsmSA==",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIIG6jCCBNKgAwIBAgITMwAAAEE7JrJwElBxvwAAAAAAQTANBgkqhkiG9w0BAQwFADCBiDELMAkGA1UEBhMCVVMxEzARB"
                            "gNVBAgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjEyM"
                            "DAGA1UEAxMpTWljcm9zb2Z0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTEwHhcNMjUwNTE0MjExMzE5WhcNM"
                            "zUxMjE0MjEyMzE5WjBgMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uMTEwLwYDVQQDE"
                            "yhNaWNyb3NvZnQgVXBkYXRlIE1ldGFkYXRhIFNpZ25pbmcgQ0EgMy4yMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICC"
                            "gKCAgEAycIssGxzKtXhGlT4ndsVheDVhHPwcb5nkj4WDHCQrlYqNdOhXXFRLwnCIa3RYNyHvlLYS0vUy7ef2DPvDBo1o"
                            "H3U0FjVhrGsyyki7bzapkeELWsDkLV3WXs63XVYgSqZjT5qq0MjlBlSka5qTbP1B2Da09XDElQRXh8LgW4ul1/o/66gL"
                            "6MGlRc0Kyw7iPALUlIAqmUnBmIypcyERN+9KWnNVlLzNqwGNaMT/BS6f8JWXoA3E4OUqs7x99bvmIEnFwRTB+zhJGn2i"
                            "ktUW1+s52SiXYZJubNvdlY065QVHn1uAfb5gyaPKWbwMYOGjzBp+AOlsIH5TVmTswyzLv6e/w6P1lYCmrSu40HEiJt8g"
                            "45mGLnxu9ytro6lesUBTLyNhZKM4otCiBVdveyzkD6xxL6e2T8KnXRSMuo+wRqP8y71P4UufOEZqrfj/wHRxgclJ4GHG"
                            "rqVJV3ZI/DRgzsAiuNz0i/doynXv5zboLtVmy3pViuW1s/2crrcUfc8/KdVA9lPS2/D1iRN9N6ByY3/vtEpocOsyQwiJ"
                            "FdfJUc5u+1L64jAa3BoiMr+xRZQ10PKT+HNIlVdM81l/IPKHG4vG2RTaQ8vJqamP1psIOHZVb6RJmSCbyWYDbSXp6bGQ"
                            "HBGXz1f0I53cyXFE4BXADjh5d0BhosdvivByFpPaYBCnzcCAwEAAaOCAXIwggFuMA4GA1UdDwEB/wQEAwIBhjAQBgkrB"
                            "gEEAYI3FQEEAwIBADAdBgNVHQ4EFgQU37H89BHAmC5ZgzQtx2MHuQnqWckwIgYDVR0lAQH/BBgwFgYIKwYBBQUHAwMGC"
                            "isGAQQBgjdMBgEwGQYJKwYBBAGCNxQCBAweCgBTAHUAYgBDAEEwDwYDVR0TAQH/BAUwAwEB/zAfBgNVHSMEGDAWgBRyL"
                            "ToCMZBDuRQFTuHqp8cx0SOJNDBaBgNVHR8EUzBRME+gTaBLhklodHRwOi8vY3JsLm1pY3Jvc29mdC5jb20vcGtpL2Nyb"
                            "C9wcm9kdWN0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3JsMF4GCCsGAQUFBwEBBFIwUDBOBggrBgEFBQcwA"
                            "oZCaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraS9jZXJ0cy9NaWNSb29DZXJBdXQyMDExXzIwMTFfMDNfMjIuY3J0M"
                            "A0GCSqGSIb3DQEBDAUAA4ICAQCfi/yDnXgx4DcB0DSgwz1KWMhGEIk9d6+pq5XtG+aFjU7/6wxzr339J46LQi70wOjp8"
                            "c+zmbmG9Hd/W8iLy+3zd687hRsXX+WdoWr4vfFdYhvyLq4kMDvha3P+hF8/Kqt5eybsJWgv6VxCiANw6uZgsNJRo2PP7"
                            "QPfJBpyll3Fpj6IRayqR6L2oTYz8hK1tL9oymXQoqvYwtQjHM9Jy5Mqqr72UMnaq2AQ1s49rc1TtdIZst0BFVwNCu6mQ"
                            "ZoBWPSJsyokCHRdP6EQI1dRpPQZVblyqDuGo/dPcmx+bAn2RKLrWnYoU8jSZ7/Knzajy5o294S6mch9u/E5VV+KSClOp"
                            "ZtzdZw9gRK5AHKsL4W+6g8QbF3y7AfBEz1Na6JRj0XcfvzgKBE6+OjjH9xQD4Q+6iDyg3J/lJ5ndBbGckqG3m2LpYiLo"
                            "UMxRHW9yK/2bSgR0jGbgKbIno5X8G85/SOn5bTvgFxuVhDdHoqpHIG83Vp0fjLl1Y9jW3IfLmhmQc+wwyi1BAb0wfN2/"
                            "6N0SPdi/FcpFr/yOUA5lI0+y3ajFZ1zVID3oHUwvpbqimkeNhOgM4laWNAviofOyS5zXhQJmZej+pg5tMlGh7HBFimvG"
                            "v3Minf7781rjLE5CFaeM2nuIxcAczi7ciSHs9hJ5hbFo8+AwqIlPc3yC5AAYlAMww==",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIID9TCCA3ugAwIBAgITMwAAAA2N8UEnSnkP7QAAAAAADTAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVB"
                            "AgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA"
                            "1UEAxM1TWljcm9zb2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMjUwNTE0M"
                            "Tk1MDMyWhcNMzUwNTE0MjAwMDMyWjBkMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uM"
                            "TUwMwYDVQQDEyxNaWNyb3NvZnQgRUNDIFVwZGF0ZSBNZXRhZGF0YSBTaWduaW5nIENBIDMuMTB2MBAGByqGSM49AgEGB"
                            "SuBBAAiA2IABH42XiDMX8162TOEnHmwcMyg4fBPPMmIqkoF+QgpQ2oPLgJxFYey9lo2rebYhqN8wofYfRXlLp5y881tD"
                            "kuxrxjUHoU4sosXUlXAOTjsmmAp88oanpxJloZxkslFSFwqWqOCAbwwggG4MA4GA1UdDwEB/wQEAwIBhjAQBgkrBgEEA"
                            "YI3FQEEAwIBADAdBgNVHQ4EFgQUAxWDdIgSmf0dk/ujqKaQYbXFg5EwIgYDVR0lAQH/BBgwFgYIKwYBBQUHAwMGCisGA"
                            "QQBgjdMBgEwGQYJKwYBBAGCNxQCBAweCgBTAHUAYgBDAEEwDwYDVR0TAQH/BAUwAwEB/zAfBgNVHSMEGDAWgBRD73CHu"
                            "J2/7IgZ3MbEa3UNdTQzCDB6BgNVHR8EczBxMG+gbaBrhmlodHRwOi8vd3d3Lm1pY3Jvc29mdC5jb20vcGtpb3BzL2Nyb"
                            "C9NaWNyb3NvZnQlMjBFQ0MlMjBQcm9kdWN0JTIwUm9vdCUyMENlcnRpZmljYXRlJTIwQXV0aG9yaXR5JTIwMjAxOC5jc"
                            "mwwgYcGCCsGAQUFBwEBBHsweTB3BggrBgEFBQcwAoZraHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jZXJ0c"
                            "y9NaWNyb3NvZnQlMjBFQ0MlMjBQcm9kdWN0JTIwUm9vdCUyMENlcnRpZmljYXRlJTIwQXV0aG9yaXR5JTIwMjAxOC5jc"
                            "nQwCgYIKoZIzj0EAwMDaAAwZQIxAIlUzIP2PWx8Yfy8U/cK0F5Co7KW9YAYySCkgN3PPxM4MXHAfpAngcih1ypgNlLlk"
                            "wIwCccvMAW/GjknqXavFCCILep9azcfyjvU0aP3eSGYMduHhlvkPvVM7a6sOMj62p1l",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIID9DCCA3ugAwIBAgITMwAAAA5H3kvETyp1IwAAAAAADjAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVB"
                            "AgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA"
                            "1UEAxM1TWljcm9zb2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMjUwNTE0M"
                            "jAxNzIyWhcNMzUwNTE0MjAyNzIyWjBkMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uM"
                            "TUwMwYDVQQDEyxNaWNyb3NvZnQgRUNDIFVwZGF0ZSBNZXRhZGF0YSBTaWduaW5nIENBIDMuMjB2MBAGByqGSM49AgEGB"
                            "SuBBAAiA2IABIGBDVjiaaXrAQQabpx3kfj0EjlyWleGCyzsxXFhkjr2JuMvhM5WZo6ze8CzP6NP0ajvNXRbwKRiZr4rN"
                            "3DOF9nlZ5/7fWoJPK2gJgK3bkh7+1MKK+C5QTXJYzQXMrS4L6OCAbwwggG4MA4GA1UdDwEB/wQEAwIBhjAQBgkrBgEEA"
                            "YI3FQEEAwIBADAdBgNVHQ4EFgQU5B5oJK6idfPx1gqDmFAXgeQ8jq4wIgYDVR0lAQH/BBgwFgYIKwYBBQUHAwMGCisGA"
                            "QQBgjdMBgEwGQYJKwYBBAGCNxQCBAweCgBTAHUAYgBDAEEwDwYDVR0TAQH/BAUwAwEB/zAfBgNVHSMEGDAWgBRD73CHu"
                            "J2/7IgZ3MbEa3UNdTQzCDB6BgNVHR8EczBxMG+gbaBrhmlodHRwOi8vd3d3Lm1pY3Jvc29mdC5jb20vcGtpb3BzL2Nyb"
                            "C9NaWNyb3NvZnQlMjBFQ0MlMjBQcm9kdWN0JTIwUm9vdCUyMENlcnRpZmljYXRlJTIwQXV0aG9yaXR5JTIwMjAxOC5jc"
                            "mwwgYcGCCsGAQUFBwEBBHsweTB3BggrBgEFBQcwAoZraHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jZXJ0c"
                            "y9NaWNyb3NvZnQlMjBFQ0MlMjBQcm9kdWN0JTIwUm9vdCUyMENlcnRpZmljYXRlJTIwQXV0aG9yaXR5JTIwMjAxOC5jc"
                            "nQwCgYIKoZIzj0EAwMDZwAwZAIwGaaAZL21scyUs20Fl5fi9MjEGScxEWFT6nv6kUuyRXuGQG953A9+27dIStV16/uuA"
                            "jBnc4NFRxFkl32Bgu6qQ5Wy+J6erKLgqNZ4IiuVFtcgLuaYjFp0BV9VIvDsLdPXJNg=",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIID7zCCA3agAwIBAgITMwAAAAyoB86V2x6sTgAAAAAADDAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVB"
                            "AgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA"
                            "1UEAxM1TWljcm9zb2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMjUwNTE0M"
                            "TkyMTM4WhcNMzUwNTE0MTkzMTM4WjBfMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uM"
                            "TAwLgYDVQQDEydNaWNyb3NvZnQgRUNDIFVwZGF0ZSBTSUggU2lnbmluZyBDQSAzLjEwdjAQBgcqhkjOPQIBBgUrgQQAI"
                            "gNiAAS+u8I7qR5BElxxq6bRiZvI1bE6db0R/jC4ghAh8ixlt6pvCAWQVBz0LxlVcLO+PRhVAHy5clk4UVug+oQXGXPd9"
                            "0wzroqYiTqHzdyzI2wXRF7BZqAdsVJJuWk8+lz2zHyjggG8MIIBuDAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCNxUBB"
                            "AMCAQAwHQYDVR0OBBYEFLzlScJuFu8ItdJSny0sDcCC+yFrMCIGA1UdJQEB/wQYMBYGCCsGAQUFBwMDBgorBgEEAYI3T"
                            "AYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUQ+9wh7idv+yIG"
                            "dzGxGt1DXU0MwgwegYDVR0fBHMwcTBvoG2ga4ZpaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jcmwvTWljc"
                            "m9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3JsMIGHB"
                            "ggrBgEFBQcBAQR7MHkwdwYIKwYBBQUHMAKGa2h0dHA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2lvcHMvY2VydHMvTWljc"
                            "m9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3J0MAoGC"
                            "CqGSM49BAMDA2cAMGQCMEROehLiMzwFKO9WqsSAlXesuBE0skdo5M17NlMylDNP+rqH3X3TKIcI+5hu1L5JTAIwElpv5"
                            "HXBObrcmThrd/xZlDpyJ7wy0Zi9HPxnf/69HVJOddQXA4D4KYuSCklMHVuw",
                           a1),
          SubCAContext < 0)
      || (SubCAContext = CreateSubCAContext(
                           L"MIID8DCCA3agAwIBAgITMwAAAAtRyJHkwl0ZWwAAAAAACzAKBggqhkjOPQQDAzCBlDELMAkGA1UEBhMCVVMxEzARBgNVB"
                            "AgTCldhc2hpbmd0b24xEDAOBgNVBAcTB1JlZG1vbmQxHjAcBgNVBAoTFU1pY3Jvc29mdCBDb3Jwb3JhdGlvbjE+MDwGA"
                            "1UEAxM1TWljcm9zb2Z0IEVDQyBQcm9kdWN0IFJvb3QgQ2VydGlmaWNhdGUgQXV0aG9yaXR5IDIwMTgwHhcNMjUwNTE0M"
                            "TgzMTMzWhcNMzUwNTE0MTg0MTMzWjBfMQswCQYDVQQGEwJVUzEeMBwGA1UEChMVTWljcm9zb2Z0IENvcnBvcmF0aW9uM"
                            "TAwLgYDVQQDEydNaWNyb3NvZnQgRUNDIFVwZGF0ZSBTSUggU2lnbmluZyBDQSAzLjIwdjAQBgcqhkjOPQIBBgUrgQQAI"
                            "gNiAATz6OgXOBOqg5XWtX4wd7A43OONj6yID45NVEcEgz2lXoavELOxeBDHytQhIk55r24wownWfOWdpSY6HNDw+fpZJ"
                            "Hrfg3mGjo017Y/EveDhXzITr/EsUk2gD7jL3gjbrE2jggG8MIIBuDAOBgNVHQ8BAf8EBAMCAYYwEAYJKwYBBAGCNxUBB"
                            "AMCAQAwHQYDVR0OBBYEFFZHRgq0fqbc+mhmCvXUFenxrePsMCIGA1UdJQEB/wQYMBYGCCsGAQUFBwMDBgorBgEEAYI3T"
                            "AYBMBkGCSsGAQQBgjcUAgQMHgoAUwB1AGIAQwBBMA8GA1UdEwEB/wQFMAMBAf8wHwYDVR0jBBgwFoAUQ+9wh7idv+yIG"
                            "dzGxGt1DXU0MwgwegYDVR0fBHMwcTBvoG2ga4ZpaHR0cDovL3d3dy5taWNyb3NvZnQuY29tL3BraW9wcy9jcmwvTWljc"
                            "m9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3JsMIGHB"
                            "ggrBgEFBQcBAQR7MHkwdwYIKwYBBQUHMAKGa2h0dHA6Ly93d3cubWljcm9zb2Z0LmNvbS9wa2lvcHMvY2VydHMvTWljc"
                            "m9zb2Z0JTIwRUNDJTIwUHJvZHVjdCUyMFJvb3QlMjBDZXJ0aWZpY2F0ZSUyMEF1dGhvcml0eSUyMDIwMTguY3J0MAoGC"
                            "CqGSM49BAMDA2gAMGUCMQDCsghBuVYE2YcK2d4XG4YDsD3WGNAsOZWVSJf0bdUsN2ZAEXhbe+JQ59yGOLF1ONECMFuSV"
                            "CBT0twZW7trTMQQBmUSInDbMQSFr0xBZ77VR/AsRkzfOr5K0S9m16paCLaFeQ==",
                           a1),
          SubCAContext < 0) )
    {
LABEL_19:
      WUTrace(0, 0, 32, 1);
      CertCloseStore(a1, 0);
    }
  }
  return (unsigned int)SubCAContext;
}

```

## disassembly

```asm
0x180057d60  mov     [rsp+arg_8], rbx
0x180057d65  push    rdi
0x180057d66  sub     rsp, 30h
0x180057d6a  xor     r8d, r8d; hCryptProv
0x180057d6d  mov     [rsp+38h+pvPara], 0; pvPara
0x180057d76  mov     rdi, rcx
0x180057d79  mov     r9d, 2000h; dwFlags
0x180057d7f  mov     edx, 10001h; dwEncodingType
0x180057d84  lea     ecx, [r8+2]; lpszStoreProvider
0x180057d88  call    cs:__imp_CertOpenStore
0x180057d8e  mov     rdx, rdi; void **
0x180057d91  lea     rcx, pszString; "MIIEaDCCA+6gAwIBAgITMwAAAAUaOuZqnuT4lwA"...
0x180057d98  mov     [rdi], rax
0x180057d9b  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057da0  mov     ebx, eax
0x180057da2  test    eax, eax
0x180057da4  js      loc_180057F32
0x180057daa  mov     rdx, rdi; void **
0x180057dad  lea     rcx, aMiieadcca6gawi; "MIIEaDCCA+6gAwIBAgITMwAAAAbeoIf7goRbkAA"...
0x180057db4  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057db9  mov     ebx, eax
0x180057dbb  test    eax, eax
0x180057dbd  js      loc_180057F32
0x180057dc3  mov     rdx, rdi; void **
0x180057dc6  lea     rcx, aMiieatcca6gawi; "MIIEaTCCA+6gAwIBAgITMwAAAAfoFBuLBbX7owA"...
0x180057dcd  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057dd2  mov     ebx, eax
0x180057dd4  test    eax, eax
0x180057dd6  js      loc_180057F32
0x180057ddc  mov     rdx, rdi; void **
0x180057ddf  lea     rcx, aMiihbtccbo2gaw_1; "MIIHBTCCBO2gAwIBAgITMwAAAAexzEAnVUg/aQA"...
0x180057de6  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057deb  mov     ebx, eax
0x180057ded  test    eax, eax
0x180057def  js      loc_180057F32
0x180057df5  mov     rdx, rdi; void **
0x180057df8  lea     rcx, aMiihbtccbo2gaw; "MIIHBTCCBO2gAwIBAgITMwAAAAhZ45TgVMcXXQA"...
0x180057dff  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e04  mov     ebx, eax
0x180057e06  test    eax, eax
0x180057e08  js      loc_180057F32
0x180057e0e  mov     rdx, rdi; void **
0x180057e11  lea     rcx, aMiihbtccbo2gaw_0; "MIIHBTCCBO2gAwIBAgITMwAAAAlShUmtVdQnFQA"...
0x180057e18  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e1d  mov     ebx, eax
0x180057e1f  test    eax, eax
0x180057e21  js      loc_180057F32
0x180057e27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x180057e2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180057e33  test    al, al
0x180057e35  jz      loc_180057F5E
0x180057e3b  mov     rdx, rdi; void **
0x180057e3e  lea     rcx, aMiig5tccbm2gaw_1; "MIIG5TCCBM2gAwIBAgITMwAAADxVlScdgs0HkwA"...
0x180057e45  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e4a  mov     ebx, eax
0x180057e4c  test    eax, eax
0x180057e4e  js      loc_180057F32
0x180057e54  mov     rdx, rdi; void **
0x180057e57  lea     rcx, aMiig5tccbm2gaw; "MIIG5TCCBM2gAwIBAgITMwAAAD2Go7M62EXyMAA"...
0x180057e5e  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e63  mov     ebx, eax
0x180057e65  test    eax, eax
0x180057e67  js      loc_180057F32
0x180057e6d  mov     rdx, rdi; void **
0x180057e70  lea     rcx, aMiig5tccbm2gaw_2; "MIIG5TCCBM2gAwIBAgITMwAAAEA6aMvS/jxdFwA"...
0x180057e77  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e7c  mov     ebx, eax
0x180057e7e  test    eax, eax
0x180057e80  js      loc_180057F32
0x180057e86  mov     rdx, rdi; void **
0x180057e89  lea     rcx, aMiig5tccbm2gaw_0; "MIIG5TCCBM2gAwIBAgITMwAAAD8gdFm/WNWTMwA"...
0x180057e90  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057e95  mov     ebx, eax
0x180057e97  test    eax, eax
0x180057e99  js      loc_180057F32
0x180057e9f  mov     rdx, rdi; void **
0x180057ea2  lea     rcx, aMiig5tccbm2gaw_3; "MIIG5TCCBM2gAwIBAgITMwAAAEN/oPFwfkwfdQA"...
0x180057ea9  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057eae  mov     ebx, eax
0x180057eb0  test    eax, eax
0x180057eb2  js      short loc_180057F32
0x180057eb4  mov     rdx, rdi; void **
0x180057eb7  lea     rcx, aMiig6jccbnkgaw_0; "MIIG6jCCBNKgAwIBAgITMwAAAD4t0wm5AC9vqQA"...
0x180057ebe  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057ec3  mov     ebx, eax
0x180057ec5  test    eax, eax
0x180057ec7  js      short loc_180057F32
0x180057ec9  mov     rdx, rdi; void **
0x180057ecc  lea     rcx, aMiig6jccbnkgaw; "MIIG6jCCBNKgAwIBAgITMwAAAEE7JrJwElBxvwA"...
0x180057ed3  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057ed8  mov     ebx, eax
0x180057eda  test    eax, eax
0x180057edc  js      short loc_180057F32
0x180057ede  mov     rdx, rdi; void **
0x180057ee1  lea     rcx, aMiid9tcca3ugaw; "MIID9TCCA3ugAwIBAgITMwAAAA2N8UEnSnkP7QA"...
0x180057ee8  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057eed  mov     ebx, eax
0x180057eef  test    eax, eax
0x180057ef1  js      short loc_180057F32
0x180057ef3  mov     rdx, rdi; void **
0x180057ef6  lea     rcx, aMiid9dcca3ugaw; "MIID9DCCA3ugAwIBAgITMwAAAA5H3kvETyp1IwA"...
0x180057efd  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057f02  mov     ebx, eax
0x180057f04  test    eax, eax
0x180057f06  js      short loc_180057F32
0x180057f08  mov     rdx, rdi; void **
0x180057f0b  lea     rcx, aMiid7zcca3agaw; "MIID7zCCA3agAwIBAgITMwAAAAyoB86V2x6sTgA"...
0x180057f12  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057f17  mov     ebx, eax
0x180057f19  test    eax, eax
0x180057f1b  js      short loc_180057F32
0x180057f1d  mov     rdx, rdi; void **
0x180057f20  lea     rcx, aMiid8dcca3agaw; "MIID8DCCA3agAwIBAgITMwAAAAtRyJHkwl0ZWwA"...
0x180057f27  call    ?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z; CreateSubCAContext(wchar_t const *,void * *)
0x180057f2c  mov     ebx, eax
0x180057f2e  test    eax, eax
0x180057f30  jns     short loc_180057F5E
0x180057f32  xor     edx, edx
0x180057f34  lea     rax, aCreatesubcasto; "CreateSubCAStore failed"
0x180057f3b  mov     [rsp+38h+var_10], rax
0x180057f40  xor     ecx, ecx
0x180057f42  mov     dword ptr [rsp+38h+pvPara], ebx
0x180057f46  lea     r9d, [rdx+1]
0x180057f4a  lea     r8d, [rdx+20h]
0x180057f4e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180057f53  xor     edx, edx; dwFlags
0x180057f55  mov     rcx, rdi; hCertStore
0x180057f58  call    cs:__imp_CertCloseStore
0x180057f5e  mov     eax, ebx
0x180057f60  mov     rbx, [rsp+38h+arg_8]
0x180057f65  add     rsp, 30h
0x180057f69  pop     rdi
0x180057f6a  retn
```
